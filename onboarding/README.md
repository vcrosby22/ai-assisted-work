# Onboarding — Cursor and agentic AI

**Who this is for:** People who have **never** used agentic AI, are **not** software developers, and consider themselves **non-technical** — but want to **shape or build products** (ideas, specs, copy, prototypes, small sites, research) with help from an AI assistant in **Cursor**.

**What this folder is:** Shareable **guides**, **checklists**, **snippets**, and **curated links**. It stays separate from machine-only Cursor config (rules and skills live in `.cursor/` only when you use a full workspace template).

## In plain language: agentic AI and Cursor

- **Agentic AI (here):** You **steer**; the assistant can **draft text**, **answer questions**, **search your project**, and **propose or apply edits to files** when you ask it to. It is not magic — it can be wrong, and you stay responsible for decisions.
- **Cursor:** A code editor (based on VS Code) with **chat** built in, **Plan** vs **Agent** modes, and optional automation. You do **not** have to become a programmer to get value: many people use it for writing, planning, and light “no-code” style work inside a folder.

## Two kinds of setup

| Setup | What you get in this repo |
|-------|---------------------------|
| **This public repo (`cursor-knowledge`)** | Onboarding, [`product-management/`](../product-management/) (e.g. glossary and PM notes), and [`cursor-knowledge/`](../cursor-knowledge/) (philosophy, reading lists). Everything linked from **[`INDEX.md`](INDEX.md)** should work on GitHub without a private monorepo. |
| **Optional full workspace** | Some teams use a **private** repo with `BACKLOG.md`, `journal/`, `.cursor/rules`, custom `/` commands, and scripts. Those paths are **not** shipped here. If you adopt that later, see **[`INDEX-full-workspace-only.md`](INDEX-full-workspace-only.md)** for how those pieces fit together. |

## Start here

1. **[`guides/building-with-agentic-ai-non-technical.md`](guides/building-with-agentic-ai-non-technical.md)** — mindset, safety, first prompts, Plan vs Agent **without** assuming a developer workflow.  
2. **[`guides/working-with-ai-context.md`](guides/working-with-ai-context.md)** — when to start a **new chat**, how to keep **truth in files**, and why long threads forget details.  
3. **[`guides/cursor-session-playbook.md`](guides/cursor-session-playbook.md)** — when you are ready to work **inside a project folder** (terminal hygiene, GitHub, static sites, journaling patterns).  
4. **[`INDEX.md`](INDEX.md)** — full catalog and reading paths.  
5. **[`checklists/first-week-cursor-non-technical.md`](checklists/first-week-cursor-non-technical.md)** — printable first-week checklist.

## Folder map

| Path | Contents |
|------|----------|
| [`guides/`](guides/) | Longer tutorials and playbooks |
| [`reference/`](reference/) | Short in-repo references (e.g. slash commands) that must work on a bare clone |
| [`checklists/`](checklists/) | First-week and pre-share lists |
| [`snippets/`](snippets/) | Copy-paste prompts or handoff templates |
| [`links/`](links/) | External references (Cursor docs, security, verification) |
| [`INDEX.md`](INDEX.md) | What exists and suggested reading order |

## Quality standard for public files

All files in this repo are held to **[`product-management/PUBLIC_DOC_QUALITY_CRITERIA.md`](../product-management/PUBLIC_DOC_QUALITY_CRITERIA.md)** — nine criteria that treat each document as a product with a user, a purpose, and a UI (the GitHub renderer). Use it when creating or reviewing content.

## Before you share your own material

1. Remove or redact secrets, tokens, internal paths, or anything you would not put on a public web page.  
2. Prefer pointing people at **[`vcrosby22/cursor-knowledge`](https://github.com/vcrosby22/cursor-knowledge)** for these guides rather than copying private journals or backlogs.
