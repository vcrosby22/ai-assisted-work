# UI design principles

**Purpose:** Visual and interaction fundamentals for any screen — web, mobile, or app.

**Harvest / review:** 2026-05

**Agent hint:** Load before component work · Always pair with [`accessibility.md`](accessibility.md)

---

## Principles

| Principle | Practice |
|-----------|----------|
| **Visual hierarchy** | One focal point per view; size/weight/color guide the eye |
| **Consistent spacing scale** | 4/8px (or token) rhythm — avoid arbitrary margins |
| **Limited type scale** | 3–5 sizes/weights for marketing sites; more only in apps |
| **Color with purpose** | Primary = action; neutrals = structure; semantic = status |
| **Alignment grid** | Columns and baselines reduce “almost polished” feel |

---

## Patterns

- **One primary CTA** per viewport on marketing pages.
- **Line length** ~45–75 characters for body copy on desktop.
- **Contrast** ≥ 4.5:1 for normal text (WCAG AA) — verify with tooling.
- **Focus states** visible for keyboard users (don't remove outlines without replacement).
- **Design tokens** for color, spacing, radius, type — single source of truth when scaling.

---

## Anti-patterns

| Avoid | Why |
|-------|-----|
| Competing bold colors | Users can't find the main action |
| Centered body paragraphs | Harder to read long text |
| Icon-only buttons without labels | Recognition fails |
| Decorative motion on load | Distracts and harms perf/a11y |

---

## Pre-ship checklist

- [ ] Clear hierarchy on hero and key pages
- [ ] Spacing consistent across sections
- [ ] Primary CTA obvious at a glance
- [ ] Type readable at mobile size

---

## Sources

- [Laws of UX](https://lawsofux.com/) — 2026-05
- [Material Design 3](https://m3.material.io/) — 2026-05
- [Practical Typography](https://practicaltypography.com/) — 2026-05
