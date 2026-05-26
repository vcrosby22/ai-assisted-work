# Checkout and payments

**Purpose:** Reduce abandonment and build trust at the highest-stakes UX moment.

**Harvest / review:** 2026-05

---

## Principles (Baymard-aligned summaries)

| Principle | Practice |
|-----------|----------|
| **Show costs early** | Shipping/tax estimates before final step when possible |
| **Minimize steps** | Each step needs a reason |
| **Inline validation** | Errors at field level, plain language |
| **Payment trust** | Recognizable methods, security cues, no sketchy redirects |
| **Mobile checkout** | Single column; large inputs; autofill-friendly |

---

## Patterns

- **Progress indicator** for multi-step checkout.
- **Order summary** persistent or reviewable on every step.
- **Error recovery** preserve cart and form data.
- **Idempotent payment** on retry (backend concern — document for full-stack).

---

## Anti-patterns

| Avoid | Why |
|-------|-----|
| Surprise account creation | Friction |
| Coupon field dominating layout | Minority use case; collapsible |
| Disabling browser autofill | Hurts speed and a11y |

---

## Pre-ship checklist

- [ ] Guest path tested end-to-end
- [ ] Mobile checkout thumb-tested
- [ ] Error states for declined card / network
- [ ] Confirmation email mentioned on success page

---

## Sources

- [Baymard — Checkout research](https://baymard.com/research/checkout-usability) — 2026-05
- [Baymard Learn](https://baymard.com/learn) — 2026-05

**Agent hint:** Nonprofit one-time gifts → [`donations-nonprofit.md`](donations-nonprofit.md)
