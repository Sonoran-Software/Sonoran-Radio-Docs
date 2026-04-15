---
description: Update the transmit and scan channels for a connected user on a specific Sonoran Radio server.
---

# Set User Channels

## Set User Channels

<mark style="color:yellow;">`PATCH`</mark> `/v2/servers/:serverId/rooms/:roomId/users/:identity/channels`

Updates the connected participant's current transmit and scan channel state.

**Headers**

| Name | Value |
| --- | --- |
| Authorization | `Bearer <community-api-key>` |
| Content-Type | `application/json` |

**Examples**

{% tabs %}
{% tab title="Sonoran.lua" %}
```lua
local response = client.radio:setUserChannelsV2(1, "91de0ce8-c571-11e9-9714-5600023b2434", {
  transmit = { 101 },
  scan = { 101, 102, 103 }
}, 1)
```
{% endtab %}
{% tab title="Sonoran.js" %}
```javascript
const response = await instance.radio?.setUserChannelsV2(
  1,
  "91de0ce8-c571-11e9-9714-5600023b2434",
  { transmit: [101], scan: [101, 102, 103] },
  1
);
```
{% endtab %}
{% tab title="Sonoran.py" %}
```python
response = instance.radio.setUserChannelsV2(
    1,
    "91de0ce8-c571-11e9-9714-5600023b2434",
    {"transmit": [101], "scan": [101, 102, 103]},
    1,
)
```
{% endtab %}
{% tab title="Sonoran.Net" %}
```csharp
var response = await sonoran.Radio.setUserChannelsV2(
    1,
    "91de0ce8-c571-11e9-9714-5600023b2434",
    new { transmit = new[] { 101 }, scan = new[] { 101, 102, 103 } },
    1
);
```
{% endtab %}
{% tab title="OpenAPI" %}
```yaml
openapi: 3.1.0
paths:
  /v2/servers/{serverId}/rooms/{roomId}/users/{identity}/channels:
    patch:
      security:
        - bearerAuth: []
```
{% endtab %}
{% tab title="cURL" %}
```bash
curl -X PATCH "https://api.sonoranradio.com/v2/servers/1/rooms/1/users/91de0ce8-c571-11e9-9714-5600023b2434/channels" \
  -H "Authorization: Bearer your-community-api-key" \
  -H "Content-Type: application/json" \
  -d "{\"transmit\":[101],\"scan\":[101,102,103]}"
```
{% endtab %}
{% endtabs %}
