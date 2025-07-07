---
description: Learn more about specific in-game error codes.
---

# Error Codes

## ERR 101: Unable to get a valid pushUrl

Sonoran Radio uses your CFX Nucleus Proxy URL to send push events from the radio to your game server. For example, this allows playing a tone on the radio to an in-game speaker.

In the event that we cannot obtain/verify your CFX Proxy URL, we try to use your server's public IP address as a backup for push events. However, sometimes this also does not work either for certain hosts.

If you receive ERR 101, then both of these did not work. You can try setting the `Config.overridePushUrl` to `http://ip:port/sonoranradio/events` where `ip:port` is the IP and port of your FiveM server (default port is 30120).

If this still does not resolve your issue, please contact your host provider as they are most likely blocking traffic to your server.

## ERR 102: No push event URL set

Sonoran Radio uses your CFX Nucleus Proxy URL to send push events from the radio to your game server.

1. Check your server console for ERR 101. ERR 101 states an issue with sending this URL to Sonoran Radio.
2. If using a non-FiveM server but still utilizing push events, ensure the `pushUrl` property is sent with a full HTTP(s) address with the [set-server-ip API endpoint](../../../developer-documentation/developer-documentation/api-endpoints/#set-server-ip).

## ERR 104: No framework detected

The Sonoran Radio FiveM resource is configured to `enforceRadioItem` which requires a framework with an inventory system. Currently we support the following frameworks: `QBCore` and `QBox` and support `qb-inventory` and `ox_inventory`. If you are utilizing a different inventory or framework, feel free to [make a suggestion](http://support.sonoransoftware.com/). If you do not utilize a framework, simply set `Config.enforceRadioItem`to false.
