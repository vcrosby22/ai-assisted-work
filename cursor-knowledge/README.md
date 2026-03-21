# Cursor Knowledge (shareable)

This folder holds the **session knowledge base** for working with Cursor and AI-assisted development: use cases, stack choices, architecture notes, and lessons learned.

**Public copy (template):** [github.com/vcrosby22/cursor-knowledge](https://github.com/vcrosby22/cursor-knowledge) — clone/fork that repo for a clean, journal-free starting point. Update it when you want to publish new sessions.

| File | Purpose |
|------|---------|
| [`CURSOR_KNOWLEDGE.md`](./CURSOR_KNOWLEDGE.md) | Main knowledge log (append new sessions at the bottom) |
| [`BACKLOG_PHILOSOPHY.md`](./BACKLOG_PHILOSOPHY.md) | Backlog definitions (PM + Scrum), intake lanes, capability-backlog structure, capture automation policy (draft) |
| [`AGENTIC_CONTEXT_URLS.md`](./AGENTIC_CONTEXT_URLS.md) | **26** curated links: LLM context windows, compaction, lost-in-middle, RAG, agent memory, Cursor rules |
| [`BACKLOG_PRODUCT_PRACTICES_URLS.md`](./BACKLOG_PRODUCT_PRACTICES_URLS.md) | Product backlog / Scrum-style reading list (13+ URLs) |
| [`MOBILE_WEB_DESIGN_PRACTICES.md`](./MOBILE_WEB_DESIGN_PRACTICES.md) | Mobile UX for data-heavy pages (tables, collapsibles, touch, WCAG); **BL-17** handoff |
| [`GIT_GITHUB_ONBOARDING.md`](./GIT_GITHUB_ONBOARDING.md) | Git & GitHub for non-technical users: patterns, gotchas, curated links; companion guide in `onboarding/guides/` |

**Prioritized backlog (repo root):** [`../BACKLOG.md`](../../BACKLOG.md) — **`onboarding/`** for shareable Cursor/agent guides.

## Maintainer

**Victoria Crosby (@vcrosby22)** · GitHub [@vcrosby22](https://github.com/vcrosby22)

## Suggested license

To make reuse unambiguous for others, add a `LICENSE` file to this repo. Common choices for documentation:

- **[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)** — others may share and adapt; they must credit you.
- **MIT** — very permissive; good if you treat this like code+docs together.

This README does not constitute legal advice; pick what fits your comfort level.

**Workspace policy (canonical):** [`onboarding/guides/public-vs-private-git-strategy.md`](../onboarding/guides/public-vs-private-git-strategy.md) — what belongs in **public** Git vs **private** (e.g. triggers cheatsheet vs backlog).

## Before you make the *whole* repo public

If `cursor-knowledge/` lives inside a larger monorepo (journals, profile, private notes, app secrets), **do not** flip the entire repository to public until you:

1. **Search for secrets** — API keys, tokens, `.env`, passwords  
   `git grep -iE 'api_key|secret|password|BEGIN RSA|ghp_'`
2. **Review `journal/` and `profile/`** — remove or exclude personal content you do not want indexed.
3. **Expand `.gitignore`** — e.g. `.env`, `**/data/*.db`, local `reports/`, OS junk.
4. **Prefer a split if unsure** — keep a **private** “workspace” repo and a **small public** repo that only contains `cursor-knowledge/`, `PROJECT_CONTEXT.md` (sanitized), and templates. Less risk, easier for others to clone.

**Recommended default:** publish only what you intend to share (this folder + curated templates), not necessarily every file in your personal workspace.

## Keeping the knowledge file in sync

- **Canonical location (private repo):** `cursor-knowledge/CURSOR_KNOWLEDGE.md`
- Root `CURSOR_KNOWLEDGE.md` is a pointer stub for legacy links.
- **Publishing:** Copy or merge sections into [vcrosby22/cursor-knowledge](https://github.com/vcrosby22/cursor-knowledge) (`CURSOR_KNOWLEDGE.md`) when you want others to see updates — never copy `.env`, journals, or profile.

After meaningful work sessions, append a dated section to `CURSOR_KNOWLEDGE.md` (session date, what you built, decisions, lessons).
