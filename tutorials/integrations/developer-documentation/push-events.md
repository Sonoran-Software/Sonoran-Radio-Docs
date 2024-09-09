---
description: Learn more about our Backend -> Game Server push events!
---

# Push Events

## Play Tone

The `play_tone` push event is sent to the game server when a dispatcher is sending a tone to one or more in-game speakers.

```json
{
    "id": "", // Community ID
    "key": "", // Community API Key (Use to authenticate)
    "payload": {
        "src": "https://s3.sonoransoftware.com/radio/system/tones/signal_100.mp3",
        "ids": [
            "STATION_123",
            "STATION_456"
        ]
    }
}
```
