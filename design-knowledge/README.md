# Design knowledge base

**Purpose:** Curated, agent-ready guidance for **any** website or product design effort — static marketing sites, nonprofit pages, full-stack apps, and e-commerce. Principles and patterns live here; external authorities are linked in [`SOURCE_INDEX.md`](SOURCE_INDEX.md).

**Harvest / review:** 2026-05 — Revisit Tier 1 links annually.

**Companion:** [`AGENTS.md`](AGENTS.md) (what to load per task) · [`context-engineering.md`](context-engineering.md) (how to load it) · [`ai-engineering/context-engineering.md`](../ai-engineering/context-engineering.md) (general LLM context)

**Cursor skills:**

| Scope | Path |
|-------|------|
| **This repo** | [`.cursor/skills/design-knowledge/SKILL.md`](../.cursor/skills/design-knowledge/SKILL.md) |
| **All workspaces** (Victoria) | `~/.cursor/skills/design-knowledge/SKILL.md` — thin router to this KB |

Both trigger on build website / new product / UI / e-commerce asks.

---

## Who this is for

- **Builders** using Cursor to ship sites and apps
- **PMs** who want research-backed UX language for reviews
- **Agents** that need predictable, link-stable references (not scraped paywalls)

## What this is not

- A copy of Baymard, WCAG, or NN/g — we **summarize** and **link**
- A replacement for project-specific research — use [`projects/`](../projects/) for vertical case studies (e.g. equine therapy nonprofit)

## Folder map

| Folder | Topics |
|--------|--------|
| [`design-thinking/`](design-thinking/) | Human-centered process, heuristic evaluation |
| [`ui-design/`](ui-design/) | Visual principles, accessibility, design systems, psychology |
| [`website-design/`](website-design/) | IA, conversion, nonprofit/mission sites |
| [`design-patterns/`](design-patterns/) | Navigation, static layouts, responsive/mobile |
| [`e-commerce/`](e-commerce/) | Catalog, checkout, donations |
| [`fashion-retail/`](fashion-retail/) | Fashion/apparel/DTC sites, drop marketing, coming-soon pages, garments without photos |
| [`backend-design/`](backend-design/) | REST APIs, architecture, security |
| [`full-stack/`](full-stack/) | Contract-first API ↔ UI alignment |

## Quick start by task

| You're building… | Start here |
|------------------|------------|
| Landing / marketing site | [`design-patterns/static-site-patterns.md`](design-patterns/static-site-patterns.md) → [`ui-design/accessibility.md`](ui-design/accessibility.md) |
| Nonprofit / mission site | [`website-design/nonprofit-and-mission.md`](website-design/nonprofit-and-mission.md) |
| Online store | [`e-commerce/fundamentals.md`](e-commerce/fundamentals.md) → [`e-commerce/checkout-and-payments.md`](e-commerce/checkout-and-payments.md) |
| Fashion / apparel brand or drop | [`fashion-retail/README.md`](fashion-retail/README.md) |
| Coming-soon / pre-launch waitlist | [`fashion-retail/coming-soon-and-prelaunch.md`](fashion-retail/coming-soon-and-prelaunch.md) |
| Web app + API | [`backend-design/api-design-rest.md`](backend-design/api-design-rest.md) → [`full-stack/contract-first.md`](full-stack/contract-first.md) |
| Design critique | [`design-thinking/ux-research-methods.md`](design-thinking/ux-research-methods.md) |

Always read [`AGENTS.md`](AGENTS.md) when scoping a new design session.
