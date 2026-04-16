---
description: Learn how to authenticate requests against the Sonoran Radio v2 API.
---

# v2 Authentication

All current v2 API endpoints require bearer authentication.

## Base URL

```http
https://api.sonoranradio.com
```

## Required Headers

| Header | Value | Description |
| --- | --- | --- |
| `Authorization` | `Bearer YOUR_API_KEY` | Authenticates the request |
| `Accept` | `application/json` | Recommended for all requests |
| `Content-Type` | `application/json` | Required for requests with a JSON body |

## Routing

Authenticated server-specific requests use:

```http
/v2/servers/{serverId}/...
```

## Example Request

{% tabs %}
{% tab title="Sonoran.lua" %}
```lua
local Sonoran = require("sonoran")

local client = Sonoran.createClient({
  product = Sonoran.productEnums.RADIO,
  communityId = "YOUR_COMMUNITY_ID",
  apiKey = "YOUR_API_KEY",
  defaultServerId = 1
})

local response = client.radio:getConnectedUsersV2(1)

print(response.success)
```
{% endtab %}

{% tab title="Sonoran.js" %}
```javascript
const Sonoran = require('@sonoransoftware/sonoran.js');

(async () => {
  const instance = new Sonoran.Instance({
    communityId: 'YOUR_COMMUNITY_ID',
    apiKey: 'YOUR_API_KEY',
    product: Sonoran.productEnums.RADIO,
    serverId: 1,
  });

  const response = await instance.radio?.getConnectedUsersV2(1);
  console.log(response);
})();
```
{% endtab %}
{% tab title="Sonoran.py" %}
```python
from sonoran import Instance, productEnums

instance = Instance(
    apiKey="YOUR_API_KEY",
    communityId="YOUR_COMMUNITY_ID",
    product=productEnums.RADIO,
    serverId=1,
)

response = instance.radio.getConnectedUsersV2(1)

print(response.success)
print(response.data if response.success else response.reason)
```
{% endtab %}
{% tab title="Sonoran.Net" %}
```csharp
using Sonoran;

using var sonoran = new SonoranClient(new SonoranClientOptions
{
    product = SonoranProduct.RADIO,
    communityId = "YOUR_COMMUNITY_ID",
    apiKey = "YOUR_API_KEY",
    defaultServerId = 1
});

var response = await sonoran.Radio.getConnectedUsersV2(1);

Console.WriteLine(response.success);
Console.WriteLine(response.data);
```
{% endtab %}

{% tab title="cURL" %}
```bash
curl --request GET \
  --url "https://api.sonoranradio.com/v2/servers/1/connected-users" \
  --header "Authorization: Bearer YOUR_API_KEY" \
  --header "Accept: application/json"
```
{% endtab %}
{% endtabs %}

## Response Formats

### Successful Requests

Successful responses return `application/json`.

### Failed Requests

Authenticated v2 request failures return `application/problem+json`.

Example:

```json
{
  "type": "https://httpstatuses.com/401",
  "title": "Unauthorized",
  "status": 401,
  "detail": "Missing Authorization header.",
  "instance": "/v2/servers/1/connected-users",
  "traceId": "00-abc123..."
}
```

## Common Authentication Errors

| Status | Cause |
| --- | --- |
| `401` | Missing `Authorization` header |
| `401` | `Authorization` header is not using the `Bearer` scheme |
| `401` | API key is invalid |
| `404` | The requested `serverId` is not configured for the authenticated community |

## Rate Limits

All v2 endpoints are rate limited per API key, not per caller IP. Limits vary by endpoint, so check the individual endpoint page for the current enforced limit.

When a request is rate limited, the API returns `429 Too Many Requests`.

These retries are intentionally limited. High-frequency integrations should still avoid bursty request patterns and should respect the published per-endpoint limits.
