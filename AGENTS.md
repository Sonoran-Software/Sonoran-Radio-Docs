# Sonoran Radio Docs Agent Notes

This file provides standing instructions for coding agents working in this repo.

## Radio V2 API Endpoint Naming

- For Sonoran Radio v2 endpoint docs, use `communityId` in URL templates and OpenAPI path parameters for `/v2/servers/{...}` routes when the route is scoped by the authenticated radio community.
- Do not document those radio v2 path parameters as `serverId` unless the backend route is genuinely keyed by a numeric server identifier rather than the community identifier.
- Keep the display URL, parameter tables, OpenAPI examples, and SDK examples aligned on the same naming.
- For room-scoped routes, continue using `roomId` alongside `communityId`.

## Radio V2 OpenAPI

- Treat the combined OpenAPI document at `developer-documentation/developer-documentation/api-endpoints-v2/README.md` as the master importable Postman/OpenAPI collection for Radio v2.
- Any addition, removal, rename, or behavior change to a documented Radio v2 endpoint must update that master OpenAPI block in the same change.
- Keep the master OpenAPI document copy-paste importable into Postman:
  - include a full `openapi` document, not a fragment
  - include `info`, `servers`, `components.securitySchemes`, and complete `paths`
  - keep path parameter names aligned with the docs convention above, especially `communityId`
- When a page includes an `OpenAPI` example tab for a single endpoint, prefer a standalone importable document there as well instead of a bare `paths:` fragment.
