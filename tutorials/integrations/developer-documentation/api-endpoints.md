---
description: Learn more about our backend API endpoints!
---

# API Endpoints

## API Base URLs

Production: `https://api.sonoranradio.com`

Development: `https://radioapi.dev.sonoransoftware.com`

## Get Community Channels

<mark style="color:green;">`POST`</mark> `/radio/get-community-channels/:id/:key`

This endpoint gets all connected users in a community.

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Body**

| Name  | Type   | Description       |
| ----- | ------ | ----------------- |
| `id`  | string | Community ID      |
| `key` | string | Community API Key |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "result": "ok",
    "groups": [
        {
            "id": 0,
            "name": "Default",
            "orderIndex": 0
        },
        {
            "id": 1,
            "name": "test",
            "orderIndex": 1
        }
    ],
    "channels": [
        {
            "id": 123,
            "groupId": 0,
            "displayName": "Patrol Ops",
            "recvFreqMajor": 40,
            "recvFreqMinor": 120,
            "xmitFreqMajor": 36,
            "xmitFreqMinor": 275,
            "repeatsXmit": true,
            "status": true,
            "orderIndex": 0,
            "talkoverProtection": false
        }
    ]
}
```
{% endtab %}
{% endtabs %}

## Get Connected Users

<mark style="color:green;">`POST`</mark> `/radio/get-connected-users/:id/:key`

This endpoint gets all connected users in a community.

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Body**

| Name  | Type   | Description       |
| ----- | ------ | ----------------- |
| `id`  | string | Community ID      |
| `key` | string | Community API Key |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "result": "ok",
    "connectedUsers": [
        {
            "identity": "91de0ce8-c571-11e9-9714-5600023b2434",
            "metadata": "{\"sonrad\":true,\"state\":{\"freqRecv\":[40,120],\"freqXmit\":[36,275],\"freqScan\":[],\"sfxKeyUp\":null,\"sfxKeyDown\":null,\"spec\":1}}"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

## Set Server IP

<mark style="color:green;">`POST`</mark> `/radio/set-server-ip`

This endpoint sets the IP address of a Sonoran Radio community, used for resource authentication.

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Body**

| Name      | Type   | Description       |
| --------- | ------ | ----------------- |
| `id`      | string | Community ID      |
| `key`     | string | Community API Key |
| `pushUrl` | string | Push Event URL    |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  "result": "ok"
}
```
{% endtab %}

{% tab title="404" %}
```json
{
  "result": "bad",
  "error": "Invalid community ID or API key"
}
```
{% endtab %}
{% endtabs %}

## Get Server Subscription from IP

<mark style="color:green;">`GET`</mark> `/radio/check-server-subscription`

This endpoint gets the subscription enumeration value of a Sonoran Radio community, based on the IP address it's called from. The IP address is set via the [set server IP endpoint](api-endpoints.md#set-server-ip).

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  "result": "ok",
  "subscription": 0 // 0 = Free, 1 = Plus, 2 = Pro
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}

## Set In-Game Speaker Locations

<mark style="color:green;">`POST`</mark> `/radio/set-server-speakers`

Sends a list of in-game speaker locations that the tone board can select.

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name        | Type                       | Description            |
| ----------- | -------------------------- | ---------------------- |
| `id`        | string                     | Community ID           |
| `key`       | string                     | Community API Key      |
| `locations` | array of `Location`objects | In-Game Tone Locations |

```json
// Location Object Array Structure
[
  {
    "label": "Fire Station 123" // STRING: Label for in-game location
    "gameId": "STATION_123" // STRING: Unique ID for in-game location
  },
  {
    "label": "Police Station ABC" // STRING: Label for in-game location
    "gameId": "STATION_456" // STRING: Unique ID for in-game location
  }
]
```

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  "result": "ok"
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}
