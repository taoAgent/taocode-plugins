---
name: api-design
description: Use when designing an API, endpoint, route, or data model — request/response shapes, error formats, naming, status codes, or versioning. Triggers on API, endpoint, route, REST, schema, payload, response, versioning.
slash: true
---

# API Design

Design APIs that are predictable and consistent, with the error cases handled.

## Steps

1. Model the resources (nouns) first, then build routes around them.
2. Name consistently — plural collections, predictable nested paths, no surprises.
3. Use predictable methods and status codes (GET/POST/PUT/PATCH/DELETE; 2xx/4xx/5xx that mean what they say).
4. Define explicit request and response schemas — every field, its type, and which are optional.
5. Use one uniform error shape across the whole API, e.g. `{ "error": { "code": "...", "message": "..." } }`.
6. Decide pagination, filtering, and sorting conventions up front and apply them everywhere.
7. Version the API from day one (path or header) so it can evolve without breaking clients.

## Rules

- Consistency over cleverness — the same patterns everywhere beat clever one-offs.
- Design the error and edge cases, not just the happy path.
- Treat the response shape as a contract; changing it is a breaking change.
