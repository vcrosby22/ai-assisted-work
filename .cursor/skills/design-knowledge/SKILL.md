---
name: design-knowledge
description: Applies the design-knowledge base for UI, website, e-commerce, accessibility (WCAG), design thinking, REST APIs, and full-stack web products. Use when the user asks to build a new product, website, landing page, web app, storefront, donation page, design system, UI/UX, frontend, checkout, or to implement/redesign a customer-facing experience—not for PM-only strategy (use product-management) unless they also need shipped UI.
---

# Design & Web Knowledge

> **Other workspaces:** Victoria’s global router is `~/.cursor/skills/design-knowledge/SKILL.md` (resolves paths into this repo). In **ai-assisted-work**, use this file — KB paths are relative below.

## Quick Start

When this skill applies:

1. Read [`design-knowledge/AGENTS.md`](../../design-knowledge/AGENTS.md) and load **only** the task-matched docs (3–5 files).
2. Read [`design-knowledge/context-engineering.md`](../../design-knowledge/context-engineering.md) if the session is large or multi-phase.
3. For **public web**, always include [`design-knowledge/ui-design/accessibility.md`](../../design-knowledge/ui-design/accessibility.md).
4. External deep links: [`design-knowledge/SOURCE_INDEX.md`](../../design-knowledge/SOURCE_INDEX.md) — summarize, do not paste paywalled corpora.

## Task routing

| User intent | Load (in order) |
|-------------|-----------------|
| **New product / greenfield web** | `AGENTS.md` → `website-design/information-architecture.md` → `design-patterns/static-site-patterns.md` → `ui-design/principles.md` → `ui-design/accessibility.md` |
| **Marketing / static site** | Same as greenfield web |
| **Nonprofit / mission site** | `website-design/nonprofit-and-mission.md` → `e-commerce/donations-nonprofit.md` → static-site + accessibility |
| **E-commerce / shop** | `e-commerce/fundamentals.md` → `e-commerce/checkout-and-payments.md` → accessibility → `design-patterns/responsive-and-mobile.md` |
| **Donate / fundraising only** | `e-commerce/donations-nonprofit.md` → `website-design/conversion-and-ctas.md` |
| **UI components / design system** | `ui-design/design-systems.md` → `ui-design/principles.md` → accessibility |
| **Full-stack app (UI + API)** | `full-stack/README.md` → `backend-design/api-design-rest.md` → `full-stack/contract-first.md` → UI docs as needed |
| **UX audit / critique** | `design-thinking/ux-research-methods.md` → `ui-design/psychology.md` |
| **Dense tables / mobile** | `design-patterns/responsive-and-mobile.md` → [`cursor-knowledge/mobile-web-design.md`](../../cursor-knowledge/mobile-web-design.md) |

## Sub-projects (`projects/`)

Load `projects/<name>/` **only** when the user names that project (e.g. equine therapy nonprofit → `projects/equine-therapy-nonprofit/`). Never load sub-projects for generic design work.

## Coordination with other skills

| Also applies? | Skill | Why |
|---------------|-------|-----|
| PRD, roadmap, discovery, prioritization | `product-management` | Outcome framing before UI build |
| Medtech / SaMD / regulated device UI | `regulated-medtech-design` | Compliance-aware constraints on top of accessibility |
| Pre-share HTML/static QA | `website-qa` (if present in workspace) | Ship checklist |

When the user says **“build a new product”** without detail: briefly clarify **PM artifacts** (problem, scope) vs **shipped experience** (pages, flows, stack). Default to loading IA + static patterns + accessibility for the implementation path.

## Operating principles

- **Patterns over copies** — extract structure from `projects/` reference sites; write original copy.
- **Accessibility is non-optional** for public sites.
- **Minimize context** — follow `AGENTS.md`; do not read the entire `design-knowledge/` tree.
- **Cite** [`SOURCE_INDEX.md`](../../design-knowledge/SOURCE_INDEX.md) when claiming research-backed UX rules.

## Outputs (typical)

- Sitemap / IA outline
- Page-section wireframe (markdown or component list)
- CTA and conversion recommendations
- Accessibility checklist for the build
- API contract sketch (full-stack)
- Pre-ship design QA notes
