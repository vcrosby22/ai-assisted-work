# Backend architecture patterns

**Purpose:** Deployable, scalable service design — especially for full-stack web products.

**Harvest / review:** 2026-05

---

## Twelve-Factor highlights

| Factor | Practice |
|--------|----------|
| **Codebase** | One repo, many deploys |
| **Dependencies** | Explicit (package lockfiles) |
| **Config** | Environment variables — never secrets in git |
| **Backing services** | DB/queue as attached resources |
| **Build, release, run** | Separate stages |
| **Processes** | Stateless app servers; state in DB/cache |
| **Port binding** | App exports HTTP via port |
| **Concurrency** | Scale out processes, not one giant machine |
| **Disposability** | Fast start, graceful shutdown |
| **Logs** | Streams to aggregator, not files-only |
| **Dev/prod parity** | Minimize environment drift |

---

## Patterns

- **Separate web and worker** processes for async jobs.
- **Health checks** `/health` for load balancers.
- **Migrations** as release step, not manual prod SQL.
- **Feature flags** in config for safe rollout.

---

## Anti-patterns

| Avoid | Why |
|-------|-----|
| Session state in app memory | Breaks horizontal scale |
| Storing uploads on local disk | Lost on redeploy |
| Same DB credentials in repo | Security incident |

---

## Sources

- [12factor.net](https://12factor.net/) — 2026-05
- [System Design Primer](https://github.com/donnemartin/system-design-primer) — 2026-05
