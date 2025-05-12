---
description: This endpoint updates the user's display name in the radio.
---

# Set User Display Name

## Set User Display Name

<mark style="color:green;">`POST`</mark> `/api/set-user-display-name`

This endpoint updates the user's transmitting and scanned channels.

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Body**

| Name          | Type   | Description       |
| ------------- | ------ | ----------------- |
| `id`          | string | Community ID      |
| `key`         | string | Community ID      |
| `accId`       | string | User Account UUID |
| `displayName` | string | New Display Name  |



**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "result": "ok"
}
```
{% endtab %}
{% endtabs %}
