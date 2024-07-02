---
description: Learn more about our backend API endpoints!
---

# API Endpoints

## API Base URLs

Production: `https://api.sonoranradio.com`

Development: `https://radioapi.dev.sonoransoftware.com`

## Set Server IP

<mark style="color:green;">`POST`</mark> `/radio/set-server-ip`

This endpoint sets the IP address of a Sonoran Radio community, used for resource authentication.

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
