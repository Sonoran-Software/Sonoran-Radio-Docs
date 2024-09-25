---
description: Learn more about specific in-game error codes.
---

# Error Codes

## ERR 101: Unable to get webBaseURL

Sonoran Radio uses your CFX Nucleus Proxy URL to send push events from the radio to your game server. For example, this allows playing a tone on the radio to an in-game speaker.

Your CFX proxy URL follows the format: `https://yourCFXUsername.users.cfx.re/`, where `yourCFXUsername` is your unique CFX username. This proxy is a built-in feature for all FiveM servers.

If you encounter this error, please reach out to your FiveM server host for assistance.

## ERR 102: No push event URL set

Sonoran Radio uses your CFX Nucleus Proxy URL to send push events from the radio to your game server.

1. Check your server console for ERR 101. ERR 101 states an issue with sending this URL to Sonoran Radio.
2. If using a non-FiveM server but still utilizing push events, ensure the `pushUrl` property is sent with a full HTTP(s) address with the [set-server-ip API endpoint](../../../integrations/developer-documentation/api-endpoints.md#set-server-ip).
