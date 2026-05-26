# E-commerce fundamentals

**Purpose:** Mental model for catalog → cart → checkout → account — applies to retail and digital goods.

**Harvest / review:** 2026-05

**Deep research:** [Baymard](https://baymard.com/) (summarize free content; link for detail)

---

## Core user jobs

| Job | UX requirement |
|-----|----------------|
| **Find** | Search, filters, sort, clear categories |
| **Evaluate** | Images, price, variants, reviews, shipping hint |
| **Buy** | Low-friction cart + checkout |
| **Return / support** | Policies visible; account order history |

---

## Principles

| Principle | Practice |
|-----------|----------|
| **Transparent pricing** | Total before pay; fees not surprise at end |
| **Guest checkout** | Don't force account creation |
| **Persistent cart** | Cross-session where logged in |
| **Stock and delivery truth** | Don't sell what you can't fulfill |

---

## Page types

| Page | Focus |
|------|--------|
| Category / PLP | Scan, filter, compare |
| PDP | Decide: gallery, specs, social proof, add to cart |
| Cart | Edit qty, shipping estimate, continue CTA |
| Checkout | Minimal steps; trust signals |
| Confirmation | Order ID, email sent, next actions |

---

## Anti-patterns

| Avoid | Why |
|-------|-----|
| Hidden shipping until last step | Top abandonment reason (Baymard) |
| Forced registration | Kills conversion |
| Tiny product thumbs on mobile | Can't evaluate |

---

## Agent hint

Checkout detail → [`checkout-and-payments.md`](checkout-and-payments.md)

---

## Sources

- [Baymard Learn](https://baymard.com/learn) — 2026-05
- [Shopify Polaris — patterns](https://polaris.shopify.com/) — 2026-05
