---
description: Learn more about our Backend -> Game Server push events!
---

# Push Events

## Push Event Address

Push events are sent to your community's `pushUrl` (full IP/port) set in the `set-server-ip` API endpoint. This endpoint should be called on startup.

## Play Tone

The `play_tone` push event is sent to the game server when a dispatcher is sending a tone to one or more in-game speakers.

```json
{
    "id": "", // Community ID
    "key": "", // Community API Key (Use to authenticate)
    "type": "play_tone",
    "payload": {
        "src": "https://s3.sonoransoftware.com/radio/system/tones/signal_100.mp3",
        "ids": [
            "STATION_123",
            "STATION_456"
        ]
    }
}
```
