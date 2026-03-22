# Project Context & Goals

**Sanitized template** — safe to share publicly. Copy into your **private** repo and customize; this version omits personal project lists and private paths.

## Who I Am (customize)

- **Role:** Technical Project Manager *(change to fit you)*
- **Context:** I use AI (especially Cursor) for my work and want to collaborate effectively with agents. I maintain a knowledge base and templates I can share with other PMs and product people.

## Goals

1. **Cursor Knowledge (primary)** — Capture use cases, technologies, architecture, and lessons from meaningful sessions (this repo's [`session-log.md`](session-log.md)).
2. **Growth** — Reflection and journaling *(recommend a **private** repo or local-only files — not published here).*
3. **Builder culture** — Turn solved problems into reusable rules, skills, and tools.
4. **Sharing** — Package learnings for others (e.g. "Cursor for PMs" style resources).

## Typical foundation in a *private* workspace

| Layer | What | Typical location (private) |
|-------|------|----------------------------|
| **Context** | Goals, current session | `PROJECT_CONTEXT.md`, `activeContext.md` |
| **Rules** | Agent behavior | `.cursor/rules/` |
| **Commands** | `/` workflows | `.cursor/commands/` |
| **Skills** | Portable capabilities | `.cursor/skills/` |
| **Hooks** | Automation | `.cursor/hooks.json` |
| **Journal** | Daily / weekly *(optional)* | `journal/` — **keep private** |
| **Profiles** | Assessments / background _(optional)_ | `profile/` — **keep private** |
| **Knowledge** | Session learnings (shareable) | **`session-log.md`** in this public repo *or* mirror from private |
| **Indexing** | `.cursorignore` | Exclude `node_modules/`, secrets, large assets |

## Conventions (template)

- After meaningful work, append to **`session-log.md`** (here or in a private mirror).
- Keep **secrets**, **tokens**, and **personal** notes out of public git.
- When a workflow is reusable, extract a **skill** or **rule** in your private workspace.

---

*Template maintained by Victoria Crosby ([@vcrosby22](https://github.com/vcrosby22)). Last updated: 2026-03-22.*
