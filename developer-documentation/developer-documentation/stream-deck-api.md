---
description: Integrate the Sonoran Radio Stream Deck plugin with desktop or FiveM.
---

# Stream Deck API

Sonoran Radio includes a Stream Deck plugin that can control the desktop application directly or route commands through a FiveM resource.

This document covers the public integration contract required for either target:

* the built-in **desktop bridge** exposed by the Electron app
* the **FiveM relay** expected by the plugin when an action target is set to `FiveM`

## Overview

Each Stream Deck action is configured with a target:

* `Desktop` uses the local Electron bridge at `http://127.0.0.1:39111`
* `FiveM` uses a local HTTP relay, defaulting to `http://127.0.0.1:17338`

The plugin uses the same command and snapshot schema for both targets. The only difference is transport:

* Desktop sends requests directly to Sonoran Radio
* FiveM sends requests to your local relay, and your relay forwards messages to and from the radio iframe/NUI

## Desktop Bridge

When Sonoran Radio Desktop is running, it starts a local HTTP bridge on:

```text
http://127.0.0.1:39111
```

### Health Check

`GET /streamdeck/health`

Response:

```json
{
  "ok": true,
  "appReady": true,
  "snapshotReady": true
}
```

### Get Current Snapshot

`GET /streamdeck/labels`

Response:

```json
{
  "ok": true,
  "appReady": true,
  "channels": [
    {
      "id": 101,
      "label": "Law 1",
      "groupId": 10,
      "groupName": "Patrol"
    }
  ],
  "state": {
    "connected": true,
    "aiEnabled": false,
    "micOpen": false,
    "primaryChIds": [101],
    "scannedChIds": [102, 103],
    "sfxVolume": 25,
    "agentGain": 100
  }
}
```

### Send a Command

`POST /streamdeck/command`

Headers:

```http
Content-Type: application/json
```

Example request:

```json
{
  "command": "transmit.ptt",
  "phase": "down"
}
```

Example response:

```json
{
  "ok": true,
  "command": "transmit.ptt"
}
```

If the command is invalid, the radio is not ready, or the payload is malformed, the bridge returns a non-200 response.

## Command Payload

All commands use the same JSON shape:

```json
{
  "command": "string",
  "phase": "down",
  "channelId": 101,
  "channelIds": [101, 102]
}
```

Fields:

| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| `command` | string | Yes | One of the supported command IDs listed below |
| `phase` | `"down"` or `"up"` | No | Defaults to `"down"` if omitted |
| `channelId` | number | Conditional | Used by single-channel commands |
| `channelIds` | number[] | Conditional | Used by multi-channel commands |

### Phase Rules

Most commands execute on `phase: "down"`.

The following hold-style commands use both phases:

* `transmit.ptt`
* `transmit.tempChannel`

For those commands:

* send `phase: "down"` when the button is pressed
* send `phase: "up"` when the button is released

### Supported Commands

| Command | Extra Fields | Description |
| --- | --- | --- |
| `group.next` | None | Move to the next channel group |
| `group.previous` | None | Move to the previous channel group |
| `channel.next` | None | Move to the next channel within the current group |
| `channel.previous` | None | Move to the previous channel within the current group |
| `transmit.toggleChannels` | `channelIds` | Toggle one or more transmit channels |
| `transmit.tempChannel` | `channelId`, `phase` | Temporarily transmit on a single channel while held |
| `scan.toggleChannels` | `channelIds` | Toggle one or more scan channels |
| `toggle.ai` | None | Toggle AI on or off |
| `transmit.ptt` | `phase` | Push-to-talk |
| `toggle.toneBoard` | None | Open or close the tone board |
| `audio.volumeUp` | None | Increase master volume |
| `audio.volumeDown` | None | Decrease master volume |
| `audio.volumeMute` | None | Toggle master mute |
| `audio.sfxUp` | None | Increase SFX volume |
| `audio.sfxDown` | None | Decrease SFX volume |
| `audio.sfxMute` | None | Toggle SFX mute |
| `audio.aiUp` | None | Increase AI volume |
| `audio.aiDown` | None | Decrease AI volume |
| `audio.aiMute` | None | Toggle AI mute |
| `audio.currentChannelsUp` | None | Increase current primary channel volume |
| `audio.currentChannelsDown` | None | Decrease current primary channel volume |
| `audio.currentChannelsMute` | None | Toggle mute for current primary channels |
| `desktop.connectedUsers` | None | Open the connected users window |
| `desktop.focusRadio` | None | Focus the Sonoran Radio desktop window |
| `desktop.toggleRadio` | None | Show or hide the Sonoran Radio desktop window |

## Snapshot Schema

The plugin reads a snapshot to populate action configuration, channel selectors, and active button state.

```json
{
  "channels": [
    {
      "id": 101,
      "label": "Law 1",
      "groupId": 10,
      "groupName": "Patrol"
    }
  ],
  "state": {
    "connected": true,
    "aiEnabled": false,
    "micOpen": false,
    "primaryChIds": [101],
    "scannedChIds": [102, 103],
    "sfxVolume": 25,
    "agentGain": 100
  }
}
```

### Channels

| Field | Type | Description |
| --- | --- | --- |
| `id` | number | Channel/profile ID |
| `label` | string | Display name shown in the plugin |
| `groupId` | number | Parent group ID |
| `groupName` | string | Parent group display name |

### State

| Field | Type | Description |
| --- | --- | --- |
| `connected` | boolean | Whether the radio is currently connected |
| `aiEnabled` | boolean | Whether AI is enabled |
| `micOpen` | boolean | Whether the microphone/PTT is currently active |
| `primaryChIds` | number[] | Current transmit channels |
| `scannedChIds` | number[] | Current scan channels |
| `sfxVolume` | number | Current SFX volume |
| `agentGain` | number | Current AI volume |

## FiveM Relay

When an action target is set to `FiveM`, the Stream Deck plugin sends requests to a local relay instead of the desktop bridge.

Default relay address:

```text
http://127.0.0.1:17338
```

The port is configurable in the Stream Deck property inspector.

### Relay Endpoint

Your resource should expose:

`POST /emit`

Headers:

```http
Content-Type: application/json
```

The plugin sends one of two request types.

### 1. Forward a Stream Deck Command

Request:

```json
{
  "eventName": "streamdeck_command",
  "payload": {
    "command": "transmit.ptt",
    "phase": "down"
  }
}
```

Your relay should:

1. forward the `payload` to the Sonoran Radio iframe/NUI as a message with type `streamdeck_command`
2. return a successful HTTP response

Recommended response:

```json
{
  "ok": true
}
```

### 2. Request the Latest Snapshot

Request:

```json
{
  "eventName": "streamdeck_snapshot_request",
  "payload": {}
}
```

Your relay should:

1. ask the Sonoran Radio iframe/NUI for the latest snapshot
2. return the snapshot in the response body under the `snapshot` key

Required response shape:

```json
{
  "ok": true,
  "snapshot": {
    "channels": [],
    "state": {
      "connected": false,
      "aiEnabled": false,
      "micOpen": false,
      "primaryChIds": [],
      "scannedChIds": [],
      "sfxVolume": 25,
      "agentGain": 100
    }
  }
}
```

## FiveM Iframe Message Contract

Inside the FiveM web view, Sonoran Radio uses iframe messages for Stream Deck integration.

### Messages Sent To Sonoran Radio

#### `streamdeck_command`

Send a standard command payload:

```json
{
  "type": "streamdeck_command",
  "payload": {
    "command": "transmit.toggleChannels",
    "channelIds": [101, 102]
  }
}
```

#### `streamdeck_snapshot_request`

Request that the iframe publish its latest state:

```json
{
  "type": "streamdeck_snapshot_request"
}
```

### Messages Sent From Sonoran Radio

#### `streamdeck_snapshot`

The iframe emits this message whenever radio/channel state changes and also in response to `streamdeck_snapshot_request`.

```json
{
  "type": "streamdeck_snapshot",
  "snapshot": {
    "channels": [
      {
        "id": 101,
        "label": "Law 1",
        "groupId": 10,
        "groupName": "Patrol"
      }
    ],
    "state": {
      "connected": true,
      "aiEnabled": false,
      "micOpen": false,
      "primaryChIds": [101],
      "scannedChIds": [102, 103],
      "sfxVolume": 25,
      "agentGain": 100
    }
  }
}
```

## Recommended FiveM Relay Flow

To ensure the plugin works reliably, the local FiveM relay should:

1. keep a cached copy of the most recent `streamdeck_snapshot`
2. forward `streamdeck_command` to the iframe immediately
3. respond to `streamdeck_snapshot_request` with the cached snapshot
4. update the cached snapshot whenever the iframe emits a new `streamdeck_snapshot`

This avoids forcing the Stream Deck plugin to wait on asynchronous browser message timing for every poll.

## Example FiveM Relay Mapping

Example relay logic:

```text
Stream Deck Plugin
  -> POST /emit { eventName: "streamdeck_command", payload: {...} }
  -> Local FiveM relay
  -> NUI message { type: "streamdeck_command", payload: {...} }

Stream Deck Plugin
  -> POST /emit { eventName: "streamdeck_snapshot_request", payload: {} }
  -> Local FiveM relay
  -> return { ok: true, snapshot: <latest cached snapshot> }

Sonoran Radio iframe
  -> postMessage { type: "streamdeck_snapshot", snapshot: {...} }
  -> Local FiveM relay caches snapshot
```

## Notes

* Use channel IDs exactly as returned by the snapshot.
* `transmit.tempChannel` and `transmit.ptt` should send both press and release phases.
* Multi-channel commands should send `channelIds` as an array of numbers.
* The FiveM relay does not need to translate command names or payload fields. Forward them exactly as documented.
