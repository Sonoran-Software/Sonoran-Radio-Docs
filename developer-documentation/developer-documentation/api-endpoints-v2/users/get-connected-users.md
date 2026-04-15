---
description: This endpoint gets all connected users for a specific Sonoran Radio server.
---

# Get Connected Users

## Get Connected Users

<mark style="color:green;">`GET`</mark> `/v2/servers/:serverId/connected-users`

Returns every currently connected radio participant for the selected server.

**Headers**

| Name | Value |
| --- | --- |
| Authorization | `Bearer <community-api-key>` |

**URL Parameters**

| Name | Type | Description |
| --- | --- | --- |
| `serverId` | integer | Sonoran Radio server ID |

**Examples**

{% tabs %}
{% tab title="Sonoran.lua" %}
```lua
local response = client.radio:getConnectedUsersV2(1)
```
{% endtab %}
{% tab title="Sonoran.js" %}
```javascript
const response = await instance.radio?.getConnectedUsersV2(1);
```
{% endtab %}
{% tab title="Sonoran.py" %}
```python
response = instance.radio.getConnectedUsersV2(1)
```
{% endtab %}
{% tab title="Sonoran.Net" %}
```csharp
var response = await sonoran.Radio.getConnectedUsersV2(1);
```
{% endtab %}
{% tab title="OpenAPI" %}
```yaml
openapi: 3.1.0
paths:
  /v2/servers/{serverId}/connected-users:
    get:
      parameters:
        - in: path
          name: serverId
          required: true
          schema:
            type: integer
            example: 1
      security:
        - bearerAuth: []
```
{% endtab %}
{% tab title="cURL" %}
```bash
curl -X GET "https://api.sonoranradio.com/v2/servers/1/connected-users" \
  -H "Authorization: Bearer your-community-api-key"
```
{% endtab %}
{% endtabs %}
