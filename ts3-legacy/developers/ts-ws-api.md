---
title: TeamSpeak Websocket API
published: true
date: 2022-05-25T19:52:02.293Z
tags: null
editor: markdown
dateCreated: 2021-10-13T04:55:08.744Z
---

# TeamSpeak Websocket API

## Connecting

The websocket is available to connect to @ `ws://localhost:33802`. FiveM blocks all connections to `localhost` and `127.0.0.1`, so use `ws://[::1]:33802` instead (the IPv6 counterpart). This is **not** a secure websocket connection.

### type field

All events **MUST** include a `type` field that will indicate the type of event that is being passed. The other fields of the event will depend on `type`.

### to\_cid field

Unless otherwise specified, all client->ws events **SHOULD** accept an optional `to_cid` field. This field dictates to which connection (or tab) the event is being passed to. If this field is ommitted, then the event will be dispatched to all connections.

## Structures

Includes all structures that will be frequently used across the client.

### frequency

```ts
type frequency = [number, number] // both integers (NOT FLOATS!)
```

### client\_state

```ts
interface client_state {
  spec: number; // incremented on major version upgrade
  /// build type of the client
  /// 0 = DEBUG
  /// 1 = PRODUCTION
  /// 2 = DEVELOPMENT
  /// since: 0.2.1
  interop: number;
  version: string;
  freq_recv: frequency;
  freq_xmit: frequency;
  
  freq_scan: frequency[];
  enable_scan: boolean;
  
  /// since: 0.1.2
  game?: client_gamestate;
}
```

### client\_gamestate

**Since**: _0.1.2_

```ts
interface client_gamestate {
  position: [number, number, number]; // integers
  /// since: 0.2.0
  radio_powered: boolean;
  /// since: 0.2.0
  tower_quality: number; // float (between 0-1)
}
```

### server\_config

```ts
interface server_config {
  id: number; // integer (unique to each server)
  pending: false;
  server_uid: string;
  /// 0 = free
  /// 1 = plus
  /// 2 = pro
  sublvl: number; // integer
  default_profile_id?: number; // integer (corresponds to profiles)
  
  patrol_channels: {
    id: number; // integer (unique to each channel + server)
    channel_uid: string;
    allow_talkover: boolean;
  }[];
  
  profiles: {
    id: number; // integer (unique to each profile + server)
    freq_recv: frequency;
    freq_xmit?: frequency;
    repeats_xmit: boolean;
  }[]
  
  disabled_vers: string[]; // array of disabled versions of plugin. can be ignored in most cases
}
```

### controller

There is one unique controller per authorized connection (tab). If the connection is not authorized to use Sonoran Radio, then the controller _does not exist_.

```ts
interface controller {
  cid: number; // integer, corresponds to the connection/tab
  server_uid: string;

  /// since 0.2.1
  nickname: string; // nickname of own client
  state: client_state; // state of own client
  config: server_config;
  in_patrol_channel: boolean;
  channel_clients: channel_client[];
}
```

### channel\_client

```ts
interface channel_client {
  id: number; // integer, corresponds to the user id
  uid: string;
  name: string; // nickname of the client
  state?: client_state;
}
```

## Client->WS Events

All events will be categorized by their `type` field, with an example of what each event will do. All events, except ones specifically stating otherwise, will accept `to_cid`.

### Errors

If an exception (error) occurs while handling an event, it will dispatch a ws->client events that contains error information.

```json
{
  "error": true, // always true in cases of errors.
  "type": string, // symbol name of exception (may be mangled, used for debugging)
  "msg": string, // the message that accompanied the exception
}
```

### get\_controllers

Will immediately produce the `recv_controllers` ws->client event

**Minimum tier**: `Free`

```json
{
  "type": "get_controllers"
}
```

### get\_controller\_data

Will immediately produce the `recv_controller_data` ws->client. Recommended to be used with `to_cid`, otherwise just use `get_controllers`.

**Minimum tier**: `Free`

```json
{
  "type": "get_controller_data"
}
```

### set\_frequencies

Sets the XMIT & RECV frequencies of own client

**Minimum tier**: `Plus`

```json
{
  "type": "set_frequencies",
  "freq_recv": frequency,
  "freq_xmit": frequency
}
```

### set\_frequencies\_scanned

**Minimum tier**: `Pro`

```json
{
  "type": "set_frequencies_scanned",
  "freqs": frequency[] // duplicates will be removed
}
```

### set\_scanning\_enabled

**Minimum tier**: `Pro`

```json
{
  "type": "set_scanning_enabled",
  "enabled": boolean
}
```

### set\_gamestate

Should be called often. If left untouched for >5m, `state.game` will revert to `null`

**Since**: 0.1.2 **Minimum tier**: `Free`

```json
{
  "type": "set_gamestate",
  "state": client_gamestate // where all fields of client_gamestate are optional
}
```

### print\_chat\_message

Prints a message to the chat (only local user can see). Supports TeamSpeak formatting (like BBCode)

**Minimum tier**: `Plus`

```json
{
  "type": "print_chat_message",
  "message": string
}
```

### change\_channel

Changes the channel of the current client

**Minimum tier**: `Plus`

```json
{
  "type": "change_channel",
  "channel_uid": string
}
```

## WS->Client Events

All events will be categorized by their `type` field, with an example of what each event will do.

### recv\_controllers

Transmitted to the connection directly after `get_controllers` is fired.

```json
{
  "type": "recv_controllers",
  "data": controller[]
}
```

### recv\_controller\_data

Transmitted to the connection directly after `get_controller_data` is fired.

```json
{
  "type": "recv_controller_data",
  "cid": number,
  "data": controller
}
```

### controller\_created

A new connection controller has been established. This means there is a new connection (tab) to communicate to.

```json
{
  "type": "controller_created",
  "data": controller
}
```

### controller\_destroyed

An exist connection controller has been destroyed. You are no longer able to communicate with it.

```json
{
  "type": "controller_destroyed",
  "cid": number
}
```

### config\_changed

The server configuration of a controller has been updated. Note that this does not necessarily mean that the fields of the config have changed, it has just received a new "version"

```json
{
  "type": "config_changed",
  "cid": number,
  "data": server_config
}
```

### frequencies\_updated

The client frequencies have updated. This may have been the result of interaction in the plugin, or from an event from a websocket client.

```json
{
  "type": "frequencies_updated",
  "cid": number,
  "freq_recv": frequency,
  "freq_xmit": frequency
}
```

### frequencies\_scanned\_updated

```json
{
  "type": "frequencies_scanned_updated",
  "cid": number,
  "enabled": boolean,
  "freqs": frequency[]
}
```

### local\_channel\_changed

The user of the plugin has changed channels.

```json
{
  "type": "local_channel_changed",
  "data": controller
}
```

### channel\_clients\_changed

There has been some update to the clients currently in the channel with the plugin user. Note that this will not broadcast if a channel client updates their state.

```json
{
  "type": "channel_clients_changed",
  "cid": number,
  "data": channel_client[]
}
```

### client\_xmit\_change

Broadcasted whenever a client in a patrol channel begins or ends a transmission. This will be broadcasted if any client speaks, even if this client cannot hear the other.

The `xmit_type` is the internal mic click identifier. `*_talk_permit` at the beginning of a transmission, and `*_squelch` is at the end of a transmission. The current values passed are (NOTE: may change in the future):

* `self_talk_permit`
* `self_squelch`
* `unit_talk_permit`
* `unit_squelch`

```json
{
  "type": "client_xmit_change",
  "cid": number,
  "client": {
    "id": number,
    "nickname": string,
    "state": client_state,
    "self": boolean
  },
  "can_hear": boolean, // indicator if we can hear the other client
  "xmit_type": string // see above
}
```
