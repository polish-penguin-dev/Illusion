# Adding Illusion

Almost There! To Make Your App Executable, You Could Add Illusion.

1. Download [Illusion Generic Scriptlet](/Scripts/IllusionGeneric.sh)
2. Modify Where Indicated;
```sh
#!/bin/sh
# Name: MODIFY (1)
# Author: MODIFY (2)
# DontUseFBInk

#Modify Below!
SOURCE_DIR="/mnt/us/documents/MODIFY (3)"
TARGET_DIR="/var/local/mesquite/MODIFY (4)"
DB="/var/local/appreg.db" #KEEP THIS!
APP_ID="MODIFY (5)"

#DO NOT MODIFY BELOW

#Copy To VAR/LOCAL/MESQUITE
if [ -d "$SOURCE_DIR" ]; then
    if [ -d "$TARGET_DIR" ]; then
        rm -rf "$TARGET_DIR"
    fi
    cp -r "$SOURCE_DIR" "$TARGET_DIR"
else
    exit 1
fi

#Redeclare To APPREG.DB 
sqlite3 "$DB" <<EOF
INSERT OR IGNORE INTO interfaces(interface) VALUES('application');

INSERT OR IGNORE INTO handlerIds(handlerId) VALUES('$APP_ID');

INSERT OR REPLACE INTO properties(handlerId,name,value) 
  VALUES('$APP_ID','lipcId','$APP_ID');
INSERT OR REPLACE INTO properties(handlerId,name,value) 
  VALUES('$APP_ID','command','/usr/bin/mesquite -l $APP_ID -c file://$TARGET_DIR/');
INSERT OR REPLACE INTO properties(handlerId,name,value) 
  VALUES('$APP_ID','supportedOrientation','U');
EOF

echo Registered $APP_ID, You May Now Launch It With LIPC.
sleep 2

#Launch With LIPC
nohup lipc-set-prop com.lab126.appmgrd start app://$APP_ID >/dev/null 2>&1 &
```

(Modifiers)
1. Name Of Scriptlet, Shows Up In Library
2. Author Of Scriptlet, Shows Up In Library
3. Name Of The Folder In Which You Are Developing Your App
4. Name Of The Folder In Which You Are Developing Your App
5. Same Namespace As Mandated In Config.XML

## You're Done!

- Distribute With `appName.sh` And `appName/` Folder!
- To Install, Drag Both To The `documents/` Folder On Your Kindle!
- Updating? Simply Drag & Drop, Replacing The Current Folder And/Or Scriptlet. NOTE; You Have To Reboot, Or Kill The Mesquite Process.
- :>

[Next Page](/Getting-Started/FAQ.md)