# Accessibility (WCAG-oriented)

**Purpose:** Non-negotiable baseline for public websites and apps — especially mission-driven sites serving diverse abilities.

**Harvest / review:** 2026-05

**Target:** **WCAG 2.2 Level AA** for most public sites (US orgs often aim here).

**Agent hint:** Load on **every** public web task

---

## POUR (four principles)

| Principle | Meaning |
|-----------|---------|
| **Perceivable** | Users can see/hear content (alt text, contrast, captions) |
| **Operable** | Keyboard, enough time, no seizure triggers, navigable |
| **Understandable** | Readable, predictable, input help |
| **Robust** | Works with assistive tech now and later |

---

## High-impact patterns

| Area | Do |
|------|-----|
| **Images** | Meaningful `alt`; decorative `alt=""` |
| **Color** | Don't rely on color alone for meaning |
| **Focus** | Visible focus ring; logical tab order |
| **Touch** | Targets ~44×44px minimum where possible |
| **Forms** | Labels linked to inputs; errors linked + described |
| **Headings** | One `h1`; don't skip levels |
| **Motion** | Respect `prefers-reduced-motion` |
| **Video** | Captions when speech matters |

---

## Anti-patterns

| Avoid | Why |
|-------|-----|
| `outline: none` without replacement | Keyboard users lost |
| Placeholder as label | Disappears; screen readers suffer |
| Auto-playing video with sound | Operable + perceivable fail |
| Low-contrast gray on white | Fails contrast for many users |

---

## Pre-ship checklist (AA-oriented)

- [ ] Keyboard-only pass through main flows
- [ ] Automated scan (axe, Lighthouse a11y) — fix criticals
- [ ] Contrast check on text and buttons
- [ ] Form labels + error messages tested
- [ ] Page has single logical `h1`

---

## Sources

- [WCAG 2.2 Quickref](https://www.w3.org/WAI/WCAG22/quickref/) — 2026-05
- [W3C WAI — WCAG overview](https://www.w3.org/WAI/standards-guidelines/wcag/) — 2026-05
- [The A11y Project](https://www.a11yproject.com/) — 2026-05
