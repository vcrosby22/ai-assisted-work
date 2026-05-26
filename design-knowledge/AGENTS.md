# Design KB — agent load map

**Purpose:** Tell Cursor (or any agent) **which files to read** for a design task. Keeps context windows focused.

**Rule:** Load **general** `design-knowledge/` docs by default. Load **`projects/<name>/`** only when the user’s active work is that sub-project.

---

## Global load order (any design task)

1. [`README.md`](README.md) — scope check
2. [`context-engineering.md`](context-engineering.md) — how much to load
3. Task-specific docs from tables below
4. [`SOURCE_INDEX.md`](SOURCE_INDEX.md) — only when you need an external deep link

**Also useful:** [`../ai-engineering/context-engineering.md`](../ai-engineering/context-engineering.md) · [`../cursor-knowledge/mobile-web-design.md`](../cursor-knowledge/mobile-web-design.md) (dense tables / mobile)

---

## Task → documents

| Task | Load (in order) |
|------|-----------------|
| **New static / marketing site** | `website-design/information-architecture.md` → `design-patterns/static-site-patterns.md` → `ui-design/principles.md` → `ui-design/accessibility.md` |
| **Nonprofit / mission-driven site** | `website-design/nonprofit-and-mission.md` → `design-patterns/static-site-patterns.md` → `e-commerce/donations-nonprofit.md` → `ui-design/accessibility.md` |
| **E-commerce storefront** | `e-commerce/fundamentals.md` → `e-commerce/checkout-and-payments.md` → `ui-design/accessibility.md` → `design-patterns/responsive-and-mobile.md` |
| **Donation / fundraising flows only** | `e-commerce/donations-nonprofit.md` → `website-design/conversion-and-ctas.md` |
| **UI components / design system** | `ui-design/design-systems.md` → `ui-design/principles.md` → `ui-design/accessibility.md` |
| **Mobile / responsive layout** | `design-patterns/responsive-and-mobile.md` → `../cursor-knowledge/mobile-web-design.md` |
| **Heuristic / UX audit** | `design-thinking/ux-research-methods.md` → `ui-design/psychology.md` |
| **REST API for web product** | `backend-design/api-design-rest.md` → `full-stack/contract-first.md` → `backend-design/security-basics.md` |
| **Backend architecture (deploy)** | `backend-design/architecture-patterns.md` → `backend-design/api-design-rest.md` |
| **Full-stack greenfield** | This file → `full-stack/README.md` → layer docs as needed |

---

## Sub-project: equine therapy nonprofit

**Only when** building that specific site:

1. [`../projects/equine-therapy-nonprofit/reference-sites.md`](../projects/equine-therapy-nonprofit/reference-sites.md)
2. [`../projects/equine-therapy-nonprofit/research-journal.md`](../projects/equine-therapy-nonprofit/research-journal.md)
3. General nonprofit row above

Do **not** load equine project files for unrelated websites.

---

## Anti-patterns for agents

| Don't | Do instead |
|-------|------------|
| Load entire `design-knowledge/` tree | Load 3–5 task-matched files |
| Paste Baymard paywalled guideline text | Summarize + link [`SOURCE_INDEX.md`](SOURCE_INDEX.md) |
| Copy competitor nonprofit copy from `projects/` | Extract **patterns**, write original copy |
| Skip accessibility on “visual” tasks | Always include `ui-design/accessibility.md` for public web |
