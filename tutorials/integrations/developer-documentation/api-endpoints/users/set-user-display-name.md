---
description: This endpoint updates the user's display name in the radio.
---

# Set User Display Name

## Set User Display Name

<mark style="color:green;">`POST`</mark> `/api/set-user-display-name/:id/:key/:identity`

This endpoint updates the user's transmitting and scanned channels.

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**URL Parameters**

| Name       | Type   | Description       |
| ---------- | ------ | ----------------- |
| `id`       | string | Community ID      |
| `key`      | string | Community API Key |
| `identity` | string | User Account UUID |

**Body**

| Name          | Type   | Description      |
| ------------- | ------ | ---------------- |
| `displayName` | string | New display name |



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
