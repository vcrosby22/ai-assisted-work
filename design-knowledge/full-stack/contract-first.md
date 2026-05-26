# Contract-first full-stack

**Purpose:** Define API shape before UI implementation drifts — shared truth for humans and agents.

**Harvest / review:** 2026-05

---

## Principles

| Principle | Practice |
|-----------|----------|
| **OpenAPI (or equivalent) first** | Spec reviewed before sprint UI work |
| **Shared types** | Generate or sync TS types from spec |
| **UI states map to API states** | Loading, empty, error, success explicit |
| **Version APIs** | UI pins to `/v1` until migration planned |

---

## Workflow

1. Write **OpenAPI** for endpoints + schemas.
2. Mock server or stub for parallel frontend work.
3. Implement backend to spec; contract tests verify.
4. Frontend uses generated client or typed fetch wrapper.

---

## UI ↔ API checklist

- [ ] Every screen documents required endpoints
- [ ] Error codes mapped to user-facing messages
- [ ] Pagination shape agreed (`items`, `nextCursor`, etc.)
- [ ] Auth flow documented (token refresh, logout)

---

## Anti-patterns

| Avoid | Why |
|-------|-----|
| “We'll document the API later” | Drift on day one |
| Frontend guessing field names | Runtime bugs |
| Breaking changes without version bump | Client outages |

---

## Sources

- [OpenAPI Specification](https://spec.openapis.org/) — 2026-05
- [`../backend-design/api-design-rest.md`](../backend-design/api-design-rest.md) — 2026-05
