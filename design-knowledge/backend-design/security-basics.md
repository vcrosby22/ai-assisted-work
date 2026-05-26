# Security basics for web products

**Purpose:** Minimum security design for public sites and APIs — not a full AppSec program.

**Harvest / review:** 2026-05

---

## OWASP-oriented priorities

| Risk area | Mitigation |
|-----------|------------|
| **Broken access control** | AuthZ on every sensitive route; least privilege |
| **Cryptographic failures** | HTTPS; hash passwords properly; no secrets in client |
| **Injection** | Parameterized queries; validate/sanitize input |
| **Insecure design** | Threat sketch before build |
| **Security misconfiguration** | Harden defaults; disable debug in prod |
| **Vulnerable components** | Dependency scanning, updates |
| **Auth failures** | MFA where appropriate; secure session cookies |

---

## Patterns

- **HttpOnly, Secure, SameSite** cookies for sessions.
- **CORS** explicit allowlist — not `*` with credentials.
- **Rate limiting** on auth and expensive endpoints.
- **CSRF** protection on cookie-based forms.
- **Content Security Policy** where feasible for XSS reduction.

---

## Anti-patterns

| Avoid | Why |
|-------|-----|
| API keys in frontend bundles | Public exposure |
| Rolling your own crypto | Use libraries + experts |
| Logging passwords or tokens | Compliance and breach risk |

---

## Sources

- [OWASP Top 10](https://owasp.org/www-project-top-ten/) — 2026-05
- [Microsoft API security](https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-design) — 2026-05
