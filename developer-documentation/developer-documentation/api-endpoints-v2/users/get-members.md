---
description: This endpoint gets paginated community members for a specific Sonoran Radio server.
---

# Get Members

## Get Members

<mark style="color:green;">`GET`</mark> `/v2/servers/:serverId/members`

> **Rate limit:** `15 requests per minute`

Returns paginated community membership data, including approval state, permission level, and per-profile access.

**Headers**

| Name | Value |
| --- | --- |
| Authorization | `Bearer <community-api-key>` |

**URL Parameters**

| Name | Type | Description |
| --- | --- | --- |
| `serverId` | integer | Sonoran Radio server ID |

**Query Parameters**

| Name | Type | Description |
| --- | --- | --- |
| `page` | integer | 1-based page number. Defaults to `1`. |
| `perPage` | integer | Page size. Defaults to `25`, maximum `100`. |
| `status` | string | Optional filter: `pending`, `approved`, or `banned`. |
| `sortBy` | string | Optional sort field: `username`, `displayName`, `approved`, `pending`, `permission`, `banned`, or `accId`. |
| `descending` | boolean | Set to `true` to sort descending. |
| `search` | string | Optional search across username, display name, and account ID. |

**Examples**

{% tabs %}
{% tab title="Sonoran.lua" %}
```lua
local response = client.radio:getMembersV2({
  page = 1,
  perPage = 25,
  status = "approved",
  sortBy = "username",
  search = "dispatch"
}, 1)
```
{% endtab %}
{% tab title="Sonoran.js" %}
```javascript
const response = await instance.radio?.getMembersV2({
  page: 1,
  perPage: 25,
  status: 'approved',
  sortBy: 'username',
  search: 'dispatch'
}, 1);
```
{% endtab %}
{% tab title="Sonoran.py" %}
```python
response = instance.radio.getMembersV2({
    "page": 1,
    "perPage": 25,
    "status": "approved",
    "sortBy": "username",
    "search": "dispatch",
}, 1)
```
{% endtab %}
{% tab title="Sonoran.Net" %}
```csharp
var response = await sonoran.Radio.getMembersV2(new GetMembersV2Query
{
    CommunityId = "YOUR_COMMUNITY_ID",
    Page = 1,
    PerPage = 25,
    Status = "approved",
    SortBy = "username",
    Search = "dispatch"
});
```
{% endtab %}
{% tab title="OpenAPI" %}
```yaml
openapi: 3.1.0
paths:
  /v2/servers/{serverId}/members:
    get:
      parameters:
        - in: path
          name: serverId
          required: true
          schema:
            type: integer
            example: 1
        - in: query
          name: page
          schema:
            type: integer
            example: 1
        - in: query
          name: perPage
          schema:
            type: integer
            example: 25
        - in: query
          name: status
          schema:
            type: string
            enum: [pending, approved, banned]
        - in: query
          name: sortBy
          schema:
            type: string
            enum: [username, displayName, approved, pending, permission, banned, accId]
        - in: query
          name: descending
          schema:
            type: boolean
            example: false
        - in: query
          name: search
          schema:
            type: string
            example: dispatch
      security:
        - bearerAuth: []
```
{% endtab %}
{% tab title="cURL" %}
```bash
curl -G "https://api.sonoranradio.com/v2/servers/1/members" \
  -H "Authorization: Bearer your-community-api-key" \
  --data-urlencode "page=1" \
  --data-urlencode "perPage=25" \
  --data-urlencode "status=approved" \
  --data-urlencode "sortBy=username" \
  --data-urlencode "search=dispatch"
```
{% endtab %}
{% endtabs %}

## Response

Successful requests return `application/json`.

```json
{
  "members": [
    {
      "accId": "91de0ce8-c571-11e9-9714-5600023b2434",
      "username": "Officer Smith",
      "displayName": "Dispatch 101",
      "permission": 34,
      "profilePerms": [
        {
          "id": 12,
          "profileId": 7,
          "canJoin": true
        }
      ],
      "approved": true,
      "pending": false,
      "banned": false
    }
  ],
  "pagination": {
    "page": 1,
    "perPage": 25,
    "total": 1,
    "totalPages": 1
  }
}
```
