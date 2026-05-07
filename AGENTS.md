# Sonoran Radio Docs Agent Notes

This file provides standing instructions for coding agents working in this repo.

## Radio V2 API Endpoint Naming

- For Sonoran Radio v2 endpoint docs, use `communityId` in URL templates and OpenAPI path parameters for `/v2/servers/{...}` routes when the route is scoped by the authenticated radio community.
- Do not document those radio v2 path parameters as `serverId` unless the backend route is genuinely keyed by a numeric server identifier rather than the community identifier.
- Keep the display URL, parameter tables, OpenAPI examples, and SDK examples aligned on the same naming.
- For room-scoped routes, continue using `roomId` alongside `communityId`.
