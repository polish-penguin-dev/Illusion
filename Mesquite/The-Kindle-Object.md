# The Kindle Object

For An In-Depth Explanation, Check Out The [Wiki](https://kindlemodding.org/wafs-and-mesquite/the-kindle-object/).

Here Are Some Useful Things You Can Do With It:

- `kindle.device.setOrientation(x);` (x = "auto", "portrait", "portraitUp", "portraitDown", "landscape", "landscapeLeft", "landscapeRight")
- `kindle.messaging.sendMessage(id, eventType, eventData)` ([Funny LIPC Stuff](https://kindlemodding.org/wafs-and-mesquite/the-kindle-object/kindle-messaging.html#kindlemessagingsendmessage))
- `kindle.net.getWirelessState()` (Returns Wifi `'on'`/`'off'`)
- `kindle.gestures` (See [This](https://kindlemodding.org/wafs-and-mesquite/the-kindle-object/kindle-gestures.html), Don't Know Why But Looks Funny. Limited By Config.XML?)
- `kindle.device.log(logServiceName, logString, logLevel)` (LOGS ARE SENT TO AMAZON! That's A Warning, But Theoretically, There's Nothing Stopping You From Sending Hate Mail To Their 'Private Servers' Or Whatever This Goes To)

[Next Section](/Illusion/Home.md)