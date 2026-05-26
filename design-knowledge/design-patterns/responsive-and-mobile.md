# Responsive and mobile

**Purpose:** Layout and interaction patterns from mobile-first through desktop.

**Harvest / review:** 2026-05

**Deep dive:** [`../../cursor-knowledge/mobile-web-design.md`](../../cursor-knowledge/mobile-web-design.md) — dense tables, accordions, static reports.

---

## Principles

| Principle | Practice |
|-----------|----------|
| **Mobile-first CSS** | Base styles for small; `min-width` breakpoints up |
| **Touch targets** | ~44px min; adequate spacing between tappable items |
| **Readable type** | 16px+ body on mobile; avoid horizontal zoom triggers |
| **Content priority** | Most important block first in DOM for narrow viewports |

---

## Patterns

- Breakpoints at content breaks, not device names only.
- **Hamburger nav** acceptable if top tasks still obvious (e.g. Donate in header).
- **Stack columns** on small screens; avoid horizontal scroll unless intentional (tables).
- Test on real device or emulator, not only narrow desktop window.

---

## Anti-patterns

| Avoid | Why |
|-------|-----|
| Hover-only interactions | No hover on touch |
| Tiny link text in paragraphs | Fitts's Law fail |
| Fixed `100vh` heroes on mobile | Address bar resize bugs |

---

## Sources

- [web.dev — Responsive design](https://web.dev/learn/design/) — 2026-05
- [WCAG — target size](https://www.w3.org/WAI/WCAG22/quickref/) — 2026-05
