# API Contract

## GET /v1/customers

Returns a paginated customer collection.

Query parameters:
- query
- page
- limit

Response includes items, total, page, limit, and nextPage.

## POST /v1/jobs

Creates asynchronous work and returns a job identifier.

## GET /v1/health

Returns service health and dependency status.

## Error contract

Errors expose a stable status code, request ID, and user-safe message. Internal stack traces are never returned to clients.

## Resilience

Transient 5xx responses should use bounded exponential backoff. 429 responses should respect Retry-After. Clients should avoid retrying deterministic 4xx validation failures.
