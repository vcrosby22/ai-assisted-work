# REST API design

**Purpose:** Predictable HTTP APIs that frontends and third parties can adopt without surprises.

**Harvest / review:** 2026-05

---

## Principles

| Principle | Practice |
|-----------|----------|
| **Resources, not actions** | `/users/123` not `/getUser` |
| **HTTP verbs mean something** | GET read, POST create, PUT/PATCH update, DELETE remove |
| **Consistent responses** | Same envelope for data, errors, pagination |
| **Version in URL** | `/v1/...` when you need breaking changes |
| **HTTPS only** | Production without exception |

---

## URL conventions

- Lowercase, hyphens: `/order-items`
- Collections plural: `/users`
- Nesting for ownership: `/users/123/orders` (don't nest too deep)

---

## Status codes (common)

| Code | Use |
|------|-----|
| 200 | OK with body |
| 201 | Created |
| 204 | Success, no body |
| 400 | Bad request (client fixable) |
| 401 | Unauthenticated |
| 403 | Forbidden |
| 404 | Not found |
| 409 | Conflict |
| 422 | Validation errors |
| 500 | Server error (log, generic message to client) |

---

## Error body pattern

```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Human-readable summary",
    "details": [{ "field": "email", "message": "Invalid format" }]
  }
}
```

---

## Patterns

- **Pagination:** `?page=2&limit=20` or cursor-based for large sets.
- **Filtering/sorting:** query params, documented.
- **Idempotency-Key** header on POST that creates side effects.
- **OpenAPI spec** as contract — generate clients and tests.

---

## Anti-patterns

| Avoid | Why |
|-------|-----|
| Verbs in URLs | Breaks HTTP caching semantics |
| Exposing DB tables 1:1 | Leaks schema; couples clients |
| Inconsistent error shapes | Client hell |

---

## Sources

- [Microsoft — Web API design](https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-design) — 2026-05
- [Postman — REST best practices](https://blog.postman.com/rest-api-best-practices/) — 2026-05
- [API/OS — Designing REST API](https://reference.apios.info/guides/designing-rest-api/) — 2026-05

**Agent hint:** [`../full-stack/contract-first.md`](../full-stack/contract-first.md)
