# Config.XML

Back To Your Project, Create A Config.XML File In The Same Folder As Your HTML, CSS, JS.

`hello/config.xml`:
```xml
<?xml version="1.0"?>
<widget id="com.you.hello" version="1.0" viewmodes="application" xmlns="http://www.w3.org/ns/widgets"
    xmlns:kindle="http://kindle.amazon.com/ns/widget-extensions">
    <name xml:lang="en">Hello Illusion!</name>
    <description xml:lang="en">An Illusion Showcase Application</description>

    <content src="index.html" />

    <!-- Permissions & Settings Standard From Kindle Store. -->
    <kindle:permissions>
        <kindle:permission name="local-port-access" />
    </kindle:permissions>
    <kindle:network>
        <kindle:asset key="user-agent" value="kindle://device-type" />
        <kindle:asset key="user-agent" value="kindle://sw-version" />
        <kindle:asset key="user-agent" value="kindle://pretty-sw-version" />
        <kindle:asset key="http-header" value="kindle://transport-method" />
        <kindle:asset key="http-header" value="kindle://country-code" />
        <kindle:asset key="initialDNS" value="false" />
        <kindle:asset key="maxConnections" value="6" />
        <kindle:asset key="maxConnectionsPerHost" value="2" />
        <kindle:asset key="maxConnectionsPerProxy" value="6" />
        <kindle:asset key="overrideProxy" value="none" />
        <kindle:asset key="enableCaching" value="false" />
    </kindle:network>

    <kindle:cookiejar>
        <kindle:asset key="persistent" value="true" />
        <kindle:asset key="usePrivateCookies" value="false" />
        <kindle:asset key="useDeviceCookies" value="true" />
        <kindle:asset key="useAccessToken" value="true" />
    </kindle:cookiejar>

    <kindle:chrome>
        <kindle:asset key="configureSearchBar" value="system" />
    </kindle:chrome>

    <kindle:gestures>
        <kindle:param name="tap" value="yes" properties="fire_on_tap:1 max_updown_delta:0" />
        <kindle:param name="swipe" value="yes" />
    </kindle:gestures>

    <feature name="http://kindle.amazon.com/apis" required="true">
        <param name="appmgr" value="yes" />
        <param name="net" value="yes" />
        <param name="todo" value="yes" />
        <param name="gestures" value="yes" />
        <param name="chrome" value="yes" />
        <param name="dev" value="yes" />
        <param name="dconfig" value="yes" />
        <param name="download" value="yes" />
        <param name="messaging" value="yes" />
        <param name="uitest" value="yes" />
        <param name="popup" value="yes" />
        <param name="bkgrnd" value="yes" />
        <param name="localprefs" value="yes" />
        <param name="device" value="yes" />
        <param name="winmgrUtils" value="yes" />
        <param name="bluetooth" value="yes" />
    </feature>

    <kindle:messaging>
        <kindle:app name="com.lab126.pillow" value="yes" />
        <kindle:app name="com.lab126.chromebar" value="yes" />
        <kindle:app name="com.lab126.readnow" value="yes" />
    </kindle:messaging>

    <!-- Removed JQuery, Non-Used JS -->
    <kindle:resources>
        <kindle:asset key="AllowHTTPSApplicationManifestCrossDomain" value="true" />
        <kindle:asset key="ApplicationCachePath" value="/var/local/mesquite/devkit/resource/appcache" />
        <kindle:asset key="ApplicationCacheLoadDelay" value="6.0" />
        <kindle:asset key="LocalStorageQuota" value="26214400" />
    </kindle:resources>

    <kindle:settings>
        <kindle:setting name="internetRequired" value="yes" />
        <kindle:setting name="saveContext" value="no" />
        <kindle:setting name="disable-wua-features" value="yes" />
    </kindle:settings>
</widget>
```

This Isn't Going To Get Into Details - For That, Check The [KindleModding](https://kindlemodding.org/wafs-and-mesquite/understanding-config-xml.html) Wiki.

You Only Need To Change The Top Part. Fields That You Could Change Are Marked "MODIFY";
```xml
<?xml version="1.0"?>
<widget id="MODIFY (1)" version="MODIFY (2)" viewmodes="application" xmlns="http://www.w3.org/ns/widgets"
    xmlns:kindle="http://kindle.amazon.com/ns/widget-extensions">
    <name xml:lang="en">MODIFY (3)</name>
    <description xml:lang="en">MODIFY (4)</description>

    <content src="MODIFY (5)" />
    ... (Everything Else, Keep The Same)
```

1. The Namespace - For Example, `xyz.penguins184.myapp`. This Doesn't Have To Match A Real Domain; You Could Do `com.your_username.appname`.
2. Version - Anything You Want, Or Just 1.0
3. App Name (English)
4. App Description (English)
5. Entrypoint (Default, "index.html")

[Next Page](/Getting-Started/Illusion-Generic-Scriptlet.md)