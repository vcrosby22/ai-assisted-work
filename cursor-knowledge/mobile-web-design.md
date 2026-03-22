# Mobile web design practices — data-heavy pages & static reports

**Purpose:** Curated patterns and authoritative links for **responsive**, **touch-friendly** layouts when content is **dense** (tables inside accordions, wide grids). Use for **BL-17** (financial-reports Pages), other static HTML, and pre-share QA.

**Harvest / review:** 2026-03 — Revisit sources annually; vendor URLs move.

**Companion:** Pre-share checks in [`.cursor/skills/website-qa/SKILL.md`](../../.cursor/skills/website-qa/SKILL.md).

---

## 1. Principles

| Principle | Practice |
|-----------|----------|
| **Content over chrome** | Reserve space for the signal users came for; trim padding/ornament on small breakpoints. |
| **Progressive disclosure** | Summary first (`<details>` summary, section title); detail without losing **orientation** (“what grid am I in?”). |
| **Minimize 2D scrolling** | Avoid **vertical scroll inside vertical scroll** plus **horizontal pan** unless headers/stickies preserve context. |
| **One primary action per view** | On mobile, don’t compete for attention between “expand everything” and “read the table.” |

---

## 2. Dense data and tables (small screens)

### Problems

- Many columns → tiny text or **horizontal pan** where **row identity** and **column headers** scroll away.
- Users lose **comparison** ability (which row is which?) without a **sticky** first column or **frozen header**.

### Patterns (high signal)

1. **Re-evaluate the table** at `sm` breakpoints — sometimes a **card-per-row** or **key–value list** beats squeezing a desktop table.
2. **Column prioritization** — Show 2–4 **primary** columns by default; “More columns” or secondary breakpoint table.
3. **Sticky header row** — Keep column titles visible while scrolling vertically.
4. **Sticky first column** — Keep row label (e.g. ticker) visible during **horizontal** scroll (CSS `position: sticky` on first `th`/`td`; watch `z-index` and shadow affordance).
5. **Filtering / subsets** — Let users reduce rows or columns (NN/g); for static reports, **pre-split** sections (e.g. mega-cap vs full list) can substitute.
6. **Horizontal scroll container** — Acceptable when **intentional**: minimum font size for data (~**12–14px** body equivalent; avoid illegible compression), `-webkit-overflow-scrolling: touch`, **visible overflow** (no `overflow: hidden` clipping without hint), optional **scroll hint** (“Swipe sideways”) on first visit or subtle fade edge.

### Alternatives to wide tables

- **Card layout:** One entity per card; primary metrics bold; secondary in muted rows.
- **Stacked rows:** Each logical row becomes a block of labeled fields.
- **Pagination / “Load more”** — Reduces DOM height and scroll fatigue (tradeoff: more taps).

---

## 3. Collapsibles (`<details>` / accordion)

| Topic | Guidance |
|-------|----------|
| **Hit target** | Enlarge `<summary>` tap area (padding); see **WCAG 2.5.8** below. |
| **Affordance** | Chevron or “expand/collapse” text; state visible in summary. |
| **Nested scroll** | Avoid **scrollable table inside scrollable page** without clear boundaries; consider **single scroll owner** or full-bleed horizontal scroll for the table only. |
| **Default open** | Limit how many heavy sections are open by default on mobile (performance + overwhelm). |

---

## 4. Touch targets and accessibility

| Criterion | Level | Requirement (summary) |
|-----------|--------|------------------------|
| **2.5.8 Target Size (Minimum)** | WCAG 2.2 **AA** | **24 × 24 CSS pixels** for pointer targets (with defined exceptions: e.g. inline text links, user-agent controls). |
| **2.5.5 Target Size (Enhanced)** | WCAG 2.2 **AAA** | **44 × 44 CSS pixels** — strong **stretch goal** for primary controls on marketing / family-facing sites. |

**Takeaway:** Treat **44px** as ideal for accordion headers and critical buttons on phones; **24px** as legal/design-system minimum for AA.

Also: sufficient **contrast** (1.4.3), **focus visible** for keyboard (don’t strip outlines without replacement), **zoom** not disabled (`viewport` must not kill pinch-zoom carelessly — `maximum-scale=1` is often harmful).

---

## 5. Orientation and “force landscape”

| Approach | Pros | Cons |
|----------|------|------|
| **Responsive layout / fewer columns** | Works in portrait; one-handed; matches user expectation. | Engineering cost. |
| **Optional hint** (“Rotate for wider tables”) | Respects user control; educates once. | Some users ignore. |
| **Lock / force landscape** (e.g. fullscreen API, aggressive messaging) | More horizontal pixels. | **NN/g:** often **annoying**; loses vertical space; bad for one-handed use; accessibility concerns. |

**Recommendation:** Prefer **layout adaptation** + **optional non-blocking hint**. Do not block content solely on orientation for an informational report.

---

## 6. Typography, viewport, safe areas

- **`viewport` meta:** Typical `width=device-width, initial-scale=1` — avoid `user-scalable=no` / `maximum-scale=1` unless there is a **very** strong reason (accessibility pushback is real).
- **`env(safe-area-inset-*)`:** Padding for notched devices (iPhone, some Android) so tap targets and tables aren’t under the home indicator.
- **Line length:** Comfortable reading width for prose; tables are exempt but **per-cell** text can wrap where acceptable.

---

## 7. Performance (mobile)

- **Large DOM** inside many expanded `<details>` sections → slow scroll and memory on mid-tier phones.
- Mitigations: **default-closed** heavy sections; **lazy** inject complex charts/tables on first expand (if JS available); split long pages.
- **Images / fonts:** Subset fonts; avoid huge inline SVG in every row if not needed.

---

## 8. Curated sources

| # | Resource | Why |
|---|----------|-----|
| 1 | [NN/g — Mobile Tables: Comparisons and Other Data Tables](https://www.nngroup.com/articles/mobile-tables/) | Canonical UX patterns: stickies, column limits, filtering, accordions. |
| 2 | [NN/g — How to Fit Big Tables on Small Screens (video)](https://www.nngroup.com/videos/big-tables-small-screens/) | Same themes in short form. |
| 3 | [W3C WAI — Web Accessibility Tutorials (tables / responsive)](https://www.w3.org/WAI/tutorials/tables/) | Semantic table structure, accessibility. |
| 4 | [W3C — Understanding SC 2.5.8 Target Size (Minimum)](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html) | **AA** 24×24 reference. |
| 5 | [W3C — Understanding SC 2.5.5 Target Size (Enhanced)](https://www.w3.org/WAI/WCAG22/Understanding/target-size-enhanced.html) | **AAA** 44×44 reference. |
| 6 | [MDN — Responsive design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design) | Breakpoints, meta viewport, fluid basics. |
| 7 | [Apple — Human Interface Guidelines (iOS / iPadOS)](https://developer.apple.com/design/human-interface-guidelines/) | Layout, touch, legibility (filter for **Layout** / **Visual design**). |
| 8 | [Material Design 3 — Understanding layout](https://m3.material.io/foundations/layout/understanding-layout/overview) | Breakpoints, adaptive windows (Google ecosystem). |
| 9 | [CSS-Tricks — Responsive Data Tables](https://css-tricks.com/responsive-data-tables/) | Implementation patterns (techniques change — triangulate with MDN/W3C). |

**Re-crawl:** Note dead links in workspace backlog or PM-style SOURCE_INDEX if this file grows.

---

## 9. Application hook — financial market report (this repo)

**Code:** [`financial-agent/src/report.py`](../../financial-agent/src/report.py) → static HTML for **GitHub Pages** (`financial-reports`).

**Current patterns (as of KB authoring):** Responsive CSS variables, `.table-scroll` / `.wide-min`, collapsible `<details>`, mobile-oriented tweaks in prior BL-17 work.

**Candidate improvements** (prioritize after device retest; maps to **BL-17**):

1. **Sticky first column** on the widest tables inside horizontal scroll.
2. **Reduce / hide non-essential columns** below breakpoint `X` (ticker + 1–2 key metrics only).
3. **Card fallback** for one high-traffic section (e.g. opportunities or market overview) on `max-width: …`.
4. **Scroll affordance** — gradient edge or one-line “Swipe for more columns” in summary.
5. **`summary` tap targets** — padding ≥ 44px height where feasible; test one-handed thumb reach.
6. **Safe-area padding** on `.risk-banner` and section cards.
7. **Optional non-blocking rotate hint** — copy-only, not a gate.

Do **not** treat this list as committed scope — validate against real phone sessions and **website-qa** checklist.

---

## 10. Related workspace artifacts

- **Backlog:** [`BACKLOG.md`](../../BACKLOG.md) **BL-17** — Mobile-optimize financial-reports Pages.
- **Story:** [`BACKLOG_STORY_DETAILS.md`](../../BACKLOG_STORY_DETAILS.md) (BL-17, BL-23 comfort with mobile).
- **Research pointer:** [`financial-agent/research/MOBILE_REPORT_UX_NOTES.md`](../../financial-agent/research/MOBILE_REPORT_UX_NOTES.md) — short link-back to this file.

---

*This document is guidance for builders, not legal accessibility sign-off. For compliance, engage expert audit on shipped templates.*
