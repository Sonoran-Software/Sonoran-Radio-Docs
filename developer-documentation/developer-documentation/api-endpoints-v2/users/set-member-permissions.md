---
description: Update member permissions for a specific Sonoran Radio server.
---

# Set Member Permissions

## Set Member Permissions

<mark style="color:yellow;">`PATCH`</mark> `/v2/servers/:serverId/members/permissions`

Updates permission bitmasks and optional profile permissions for one or more server members.

**Headers**

| Name | Value |
| --- | --- |
| Authorization | `Bearer <community-api-key>` |
| Content-Type | `application/json` |

**Examples**

{% tabs %}
{% tab title="Sonoran.lua" %}
```lua
local response = client.radio:setMemberPermissionsV2({
  {
    accId = "91de0ce8-c571-11e9-9714-5600023b2434",
    perm = 34
  }
}, 1)
```
{% endtab %}
{% tab title="Sonoran.js" %}
```javascript
const response = await instance.radio?.setMemberPermissionsV2([
  {
    accId: "91de0ce8-c571-11e9-9714-5600023b2434",
    perm: 34
  }
], 1);
```
{% endtab %}
{% tab title="Sonoran.py" %}
```python
response = instance.radio.setMemberPermissionsV2([
    {
        "accId": "91de0ce8-c571-11e9-9714-5600023b2434",
        "perm": 34
    }
], 1)
```
{% endtab %}
{% tab title="Sonoran.Net" %}
```csharp
var response = await sonoran.Radio.setMemberPermissionsV2(new[]
{
    new MemberPermissionV2Change
    {
        AccId = "91de0ce8-c571-11e9-9714-5600023b2434",
        Perm = 34
    }
}, 1);
```
{% endtab %}
{% tab title="OpenAPI" %}
```yaml
openapi: 3.1.0
paths:
  /v2/servers/{serverId}/members/permissions:
    patch:
      security:
        - bearerAuth: []
```
{% endtab %}
{% tab title="cURL" %}
```bash
curl -X PATCH "https://api.sonoranradio.com/v2/servers/1/members/permissions" \
  -H "Authorization: Bearer your-community-api-key" \
  -H "Content-Type: application/json" \
  -d "{\"userPerms\":[{\"accId\":\"91de0ce8-c571-11e9-9714-5600023b2434\",\"perm\":34}]}"
```
{% endtab %}
{% endtabs %}
