---
description: Sonoran Radio v2 API endpoints with bearer auth, server-scoped URLs, and documented per-endpoint rate limits.
---

# API Endpoints v2

Sonoran Radio v2 moves authentication to the `Authorization` header and scopes server-specific requests with `serverId` in the URL.

## Available v2 Docs

### Libraries

Use the official Sonoran SDK libraries if you want package-managed helpers for the v2 API.

{% content-ref url="libraries.md" %}
[libraries](libraries.md)
{% endcontent-ref %}

### Authentication

Start here for bearer authentication, required headers, server-scoped routing, and common error formats.

{% content-ref url="authentication.md" %}
[authentication](authentication.md)
{% endcontent-ref %}

### Users

User endpoints cover connected users, member approval, moderation, permissions, and channel assignment.

{% content-ref url="users/" %}
[users](users/)
{% endcontent-ref %}

### Channels

Channel endpoints cover channel discovery and tone playback operations.

{% content-ref url="channels/" %}
[channels](channels/)
{% endcontent-ref %}

### Community Server

Community server endpoints cover server IP registration, subscription lookup, and in-game speaker location updates.

{% content-ref url="community-server/" %}
[community-server](community-server/)
{% endcontent-ref %}

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
