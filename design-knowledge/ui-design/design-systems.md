# Design systems

**Purpose:** When to use tokens, components, and public design systems — and how they connect design to code.

**Harvest / review:** 2026-05

**Agent hint:** Load for component libraries · See [`../design-patterns/responsive-and-mobile.md`](../design-patterns/responsive-and-mobile.md)

---

## Principles

| Principle | Practice |
|-----------|----------|
| **Tokens first** | Color, space, type, radius as named variables |
| **Components, not pages** | Reuse buttons, inputs, cards with documented states |
| **Docs = code** | Design system docs live in repo (docs-as-code) |
| **Accessibility baked in** | Components meet WCAG in default state |

---

## When to adopt what

| Situation | Approach |
|-----------|----------|
| Marketing site, few pages | Light tokens + CSS; optional shadcn/Tailwind |
| React product | shadcn/ui, MUI, or Polaris (e-commerce) |
| Government / high a11y | GOV.UK, USWDS patterns |
| Mobile-native feel | Material 3 guidelines |

---

## Open systems worth studying (T3)

| System | Best for |
|--------|----------|
| [GOV.UK](https://design-system.service.gov.uk/) | Forms, service patterns, accessibility |
| [Polaris](https://polaris.shopify.com/) | Merchant/admin e-commerce UI |
| [Material 3](https://m3.material.io/) | Cross-platform tokens and motion |
| [shadcn/ui](https://ui.shadcn.com/docs) | Own-the-code React components |

---

## Anti-patterns

| Avoid | Why |
|-------|-----|
| Copying DS without tokens | Drift between design and code |
| Two competing button styles | Breaks consistency heuristic |
| Importing entire MUI for one button | Bundle bloat |

---

## Sources

- [shadcn/ui docs](https://ui.shadcn.com/docs) — 2026-05
- [GOV.UK Design System](https://design-system.service.gov.uk/) — 2026-05
- [Material Design 3](https://m3.material.io/) — 2026-05

See full list: [`../SOURCE_INDEX.md`](../SOURCE_INDEX.md).
