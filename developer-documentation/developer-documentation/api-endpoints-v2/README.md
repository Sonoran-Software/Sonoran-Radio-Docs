---
description: Sonoran Radio v2 API endpoints with bearer auth and server-scoped URLs.
---

# API Endpoints v2

## API Base URLs

Production: `https://api.sonoranradio.com`

Development: `https://radioapi.dev.sonoransoftware.com`

## Authentication

All authenticated v2 endpoints use:

* `Authorization: Bearer <community-api-key>`

The API key is no longer sent in the request body or URL.

## Routing

Community servers are addressed through the URL with `serverId`:

* `/v2/servers/:serverId/...`

This lets one community API key address multiple servers without reusing the old v1 request format.
