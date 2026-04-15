---
description: Update stored member display names for a specific Sonoran Radio server.
---

# Set Member Display Names

## Set Member Display Names

<mark style="color:yellow;">`PATCH`</mark> `/v2/servers/:serverId/members/display-names`

Updates member nicknames for the selected server.

**Headers**

| Name | Value |
| --- | --- |
| Authorization | `Bearer <community-api-key>` |
| Content-Type | `application/json` |

**Examples**

{% tabs %}
{% tab title="Sonoran.lua" %}
```lua
local response = client.radio:setMemberDisplayNamesV2({
  {
    accId = "91de0ce8-c571-11e9-9714-5600023b2434",
    nickname = "Chief Miller"
  }
}, 1)
```
{% endtab %}
{% tab title="Sonoran.js" %}
```javascript
const response = await instance.radio?.setMemberDisplayNamesV2([
  {
    accId: "91de0ce8-c571-11e9-9714-5600023b2434",
    nickname: "Chief Miller"
  }
], 1);
```
{% endtab %}
{% tab title="Sonoran.py" %}
```python
response = instance.radio.setMemberDisplayNamesV2([
    {
        "accId": "91de0ce8-c571-11e9-9714-5600023b2434",
        "nickname": "Chief Miller"
    }
], 1)
```
{% endtab %}
{% tab title="Sonoran.Net" %}
```csharp
var response = await sonoran.Radio.setMemberDisplayNamesV2(new[]
{
    new MemberDisplayNameV2Change
    {
        AccId = "91de0ce8-c571-11e9-9714-5600023b2434",
        Nickname = "Chief Miller"
    }
}, 1);
```
{% endtab %}
{% tab title="OpenAPI" %}
```yaml
openapi: 3.1.0
paths:
  /v2/servers/{serverId}/members/display-names:
    patch:
      security:
        - bearerAuth: []
```
{% endtab %}
{% tab title="cURL" %}
```bash
curl -X PATCH "https://api.sonoranradio.com/v2/servers/1/members/display-names" \
  -H "Authorization: Bearer your-community-api-key" \
  -H "Content-Type: application/json" \
  -d "{\"accNicknames\":[{\"accId\":\"91de0ce8-c571-11e9-9714-5600023b2434\",\"nickname\":\"Chief Miller\"}]}"
```
{% endtab %}
{% endtabs %}
