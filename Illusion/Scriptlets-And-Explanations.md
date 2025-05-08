# Scriptlets & Explanations

This Goes Through Illusion Scriptlets, And How They Work Line By Line.

NOTE; Right Now, Only Illusion Generic Scriptlet Is Released. One That Downloads App From GitHub, Is (Hopefully) Soon To Come.

[Illusion Generic](/Scripts/IllusionGeneric.sh); (Below Variables)

```sh
if [ -d "$SOURCE_DIR" ]; then
    if [ -d "$TARGET_DIR" ]; then
        rm -rf "$TARGET_DIR"
    fi
    cp -r "$SOURCE_DIR" "$TARGET_DIR"
else
    exit 1
fi
```

Explanation: If The Directory Packaged With The Scriptlet, As Mandated In `$SOURCE_DIR`, Is Nonexistent, It Automatically Exits. Otherwise, If It Has Been Already Copied To `var/local/mesquite/x`, `var/local/mesquite/x` Gets Deleted (So You Can See Updates), And Either Way `$SOURCE_DIR` Gets Copied To `$TARGET_DIR`. 

```sh
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
```

Explanation: Add The Application To `APPREG.DB`. It's Quite Simple, Looked Through It With DB Explorer And Somehow Wound Up With This. I *don't* Think This Declaration Influences App Functionality Too Much (`supportedOrientation`?), Moreso Config.XML.

```sh
sleep 2
```

Explanation: Don't Know Why, Maybe Registration Is Slow, BUT THIS IS REQUIRED! Didn't Work For Many Without.

```sh
nohup lipc-set-prop com.lab126.appmgrd start app://$APP_ID >/dev/null 2>&1 &
```

Explanation: Nohup Is Required As Scriptlet Likes To Exit Prematurely. Uses `lipc` To Run The Application.

[Back To Start](/README.md)