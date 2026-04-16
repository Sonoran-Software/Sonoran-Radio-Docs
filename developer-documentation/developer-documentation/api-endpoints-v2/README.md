---
description: Sonoran Radio v2 API endpoints with bearer auth, server-scoped URLs, and documented per-endpoint rate limits.
---

# API Endpoints v2

Sonoran Radio v2 moves authentication to the `Authorization` header and scopes server-specific requests with `serverId` in the URL.

## Base URL

```http
https://api.sonoranradio.com
```

## Required Headers

| Header | Value | Description |
| --- | --- | --- |
| `Authorization` | `Bearer YOUR_API_KEY` | Required for authenticated v2 endpoints |
| `Accept` | `application/json` | Recommended for all requests |
| `Content-Type` | `application/json` | Required for requests with a JSON body |

## Routing

Authenticated server-specific requests use:

```http
/v2/servers/{serverId}/...
```

This allows one community API key to interact with multiple Radio servers without sharing a single rate-limit bucket tied to the old v1 format.

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
  "instance": "/v2/servers/1/channels",
  "traceId": "00-abc123..."
}
```

## Common Errors

| Status | Cause |
| --- | --- |
| `400` | Validation failed for one or more request values |
| `401` | Missing or invalid bearer token |
| `404` | `serverId` is not available to the authenticated API key |
| `404` | Requested room, member, or participant was not found |
| `429` | Rate limit exceeded for the endpoint |

## Rate Limits

All authenticated v2 endpoints are rate limited per API key, not per caller IP. Limits vary by endpoint, so each endpoint page includes the published limit for that route.

When a request is rate limited, the gateway returns `429 Too Many Requests`.

High-frequency integrations should respect the published per-endpoint limits even if a small internal buffer exists.

## Libraries

Use the official Sonoran SDK libraries if you want package-managed helpers for the v2 API.

{% content-ref url="libraries.md" %}
[libraries](libraries.md)
{% endcontent-ref %}
