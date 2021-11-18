---
title: TeamSpeak Websocket API
description: 
published: true
date: 2021-11-18T07:29:14.118Z
tags: 
editor: markdown
dateCreated: 2021-10-13T04:55:08.744Z
---

# Connecting

The websocket is available to connect to @ `ws://localhost:33802`. FiveM blocks all connections to `localhost` and `127.0.0.1`, so use `ws://[::1]:33802` instead (the IPv6 counterpart). This is **not** a secure websocket connection.

## type field

All events **MUST** include a `type` field that will indicate the type of event that is being passed. The other fields of the event will depend on `type`.

## to_cid field

 Unless otherwise specified, all client->ws events **SHOULD** accept an optional `to_cid` field. This field dictates to which connection (or tab) the event is being passed to. If this field is ommitted, then the event will be dispatched to all connections.
 
 # Structures

Includes all structures that will be frequently used across the client.

## <var>frequency</var>

```ts
type frequency = [number, number] // both integers (NOT FLOATS!)
```

## <var>client_state</var>
 
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

## <var>client_gamestate</var>

**Since**: *0.1.2*

```ts
interface client_gamestate {
  position: [number, number, number]; // integers
  /// since: 0.2.0
  radio_powered: boolean;
  /// since: 0.2.0
  tower_quality: number; // float (between 0-1)
}
```

## <var>server_config</var>

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

## <var>controller</var>

There is one unique controller per authorized connection (tab). If the connection is not authorized to use Sonoran Radio, then the controller *does not exist*.

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

## <var>channel_client</var>

```ts
interface channel_client {
  id: number; // integer, corresponds to the user id
  uid: string;
  name: string; // nickname of the client
  state?: client_state;
}
```

# Client->WS Events
 
All events will be categorized by their `type` field, with an example of what each event will do. All events, except ones specifically stating otherwise, will accept `to_cid`.

## Errors

If an exception (error) occurs while handling an event, it will dispatch a ws->client events that contains error information.
```json
{
  "error": true, // always true in cases of errors.
  "type": string, // symbol name of exception (may be mangled, used for debugging)
  "msg": string, // the message that accompanied the exception
}
```

## <var>get_controllers</var>
 
Will immediately produce the `recv_controllers` ws->client event

**Minimum tier**: `Free`

```json
{
  "type": "get_controllers"
}
```

## <var>get_controller_data</var>

Will immediately produce the `recv_controller_data` ws->client. Recommended to be used with `to_cid`, otherwise just use `get_controllers`.

**Minimum tier**: `Free`

```json
{
  "type": "get_controller_data"
}
```

## <var>set_frequencies</var>

Sets the XMIT & RECV frequencies of own client

**Minimum tier**: `Plus`

```json
{
  "type": "set_frequencies",
  "freq_recv": frequency,
  "freq_xmit": frequency
}
```

## <var>set_frequencies_scanned</var>

**Minimum tier**: `Pro`

```json
{
  "type": "set_frequencies_scanned",
  "freqs": frequency[] // duplicates will be removed
}
```

## <var>set_scanning_enabled</var>

**Minimum tier**: `Pro`

```json
{
  "type": "set_scanning_enabled",
  "enabled": boolean
}
```

## <var>set_gamestate</var>

Should be called often. If left untouched for >5m, `state.game` will revert to `null`

**Since**: 0.1.2
**Minimum tier**: `Free`

```json
{
  "type": "set_gamestate",
  "state": client_gamestate // where all fields of client_gamestate are optional
}
```

## <var>print_chat_message</var>

Prints a message to the chat (only local user can see). Supports TeamSpeak formatting (like BBCode)

**Minimum tier**: `Plus`

```json
{
  "type": "print_chat_message",
  "message": string
}
```

# WS->Client Events
 
All events will be categorized by their `type` field, with an example of what each event will do.

## <var>recv_controllers</var>

Transmitted to the connection directly after `get_controllers` is fired.

```json
{
  "type": "recv_controllers",
  "data": controller[]
}
```

## <var>recv_controller_data</var>

Transmitted to the connection directly after `get_controller_data` is fired.

```json
{
  "type": "recv_controller_data",
  "cid": number,
  "data": controller
}
```

## <var>controller_created</var>

A new connection controller has been established. This means there is a new connection (tab) to communicate to.

```json
{
  "type": "controller_created",
  "data": controller
}
```

## <var>controller_destroyed</var>

An exist connection controller has been destroyed. You are no longer able to communicate with it.

```json
{
  "type": "controller_destroyed",
  "cid": number
}
```

## <var>config_changed</var>

The server configuration of a controller has been updated. Note that this does not necessarily mean that the fields of the config have changed, it has just received a new "version"

```json
{
  "type": "config_changed",
  "cid": number,
  "data": server_config
}
```

## <var>frequencies_updated</var>

The client frequencies have updated. This may have been the result of interaction in the plugin, or from an event from a websocket client.

```json
{
  "type": "frequencies_updated",
  "cid": number,
  "freq_recv": frequency,
  "freq_xmit": frequency
}
```

## <var>frequencies_scanned_updated</var>

```json
{
  "type": "frequencies_scanned_updated",
  "cid": number,
  "enabled": boolean,
  "freqs": frequency[]
}
```

## <var>local_channel_changed</var>

The user of the plugin has changed channels.

```json
{
  "type": "local_channel_changed",
  "data": controller
}
```

## <var>channel_clients_changed</var>

There has been some update to the clients currently in the channel with the plugin user. Note that this will not broadcast if a channel client updates their state.

```json
{
  "type": "channel_clients_changed",
  "cid": number,
  "data": channel_client[]
}
```