# Public vs private Git — what we ship where

**Purpose:** One place to decide what belongs in a **public** GitHub repo (or public HTML handbook) vs what stays in the **private** workspace. Review this before changing repo visibility or publishing a fork.

**Related:** [Cursor knowledge README](../../cursor-knowledge/README.md) (public template notes), [Handbook build](../../../scripts/README-workspace-handbook.md) (includes **`--public`** sync + `mkdocs.public.yml`).

---

## Definitions

| Term | Meaning |
|------|---------|
| **Private workspace repo** | Canonical clone of **`where_cursor_feels_home`** (or your private monorepo). Holds journals, backlog, personal context, and everything else. |
| **Public Git** | Any repo or branch meant for **others to clone** or **browse on GitHub** without authentication. Treat as **permanent and searchable**. |
| **Public handbook** | HTML from MkDocs after **`sync_workspace_handbook.py --public`** + **`mkdocs build -f mkdocs.public.yml`** — **no** canonical backlog files in the tree. |

---

## Policy (Victoria — 2026)

| Topic | Visibility | Rationale |
|-------|------------|-----------|
| **[`cursor-triggers-and-prompts.md`](cursor-triggers-and-prompts.md)** (slash commands, glossary phrases, Plan vs Agent) | **Public-friendly** | Onboarding others to Cursor; no secrets by design. |
| **Canonical backlog** — `BACKLOG.md`, `BACKLOG_STORY_DETAILS.md`, `BACKLOG_INBOX.md`, and the `backlog/` ticketing tree (repo **root** + `backlog/`) | **Private only** | Priorities, notes, and story text can reveal plans, people, and timing. |
| **`journal/`** | **Private only** | Personal and session narrative. |
| **`.env`, keys, tokens** | **Never public** | Security rules in **`.cursor/rules/security.mdc`**. |
| **Handbook / KB slices** (e.g. `cursor-knowledge/` how-tos, `GLOSSARY.md`, playbooks) | **Public OK** after quick scan | Sanitize names or one-off details if needed. |
| **`PROJECT_CONTEXT.md` / `PRIMARY_OBJECTIVES.md`** | **Case-by-case** | Often fine for a **template**; redact personal bio or specific names before a **wide** public fork. |

**Principle:** *If it is a **prioritized list of what you will do** (backlog) or **diary-like capture** (journal), it stays private. If it **teaches a workflow** (triggers cheatsheet, git basics, glossary), it can be public.*

---

## Where to push (routing)

**Before `git push`,** run **`git remote get-url origin`** (or `git remote -v`) and confirm you are in the **right directory** for the **right remote**. Wrong-folder pushes are how private notes or half-synced code end up in the wrong place.

| What you are saving | Run git from | Expected `origin` (pattern) | Visibility |
|---------------------|--------------|-------------------------------|------------|
| **Whole workspace** — journal, backlog, `.cursor`, `financial-agent/` source, onboarding, etc. | Monorepo **root** (`where_cursor_feels_home`) | Host/path contains **`where_cursor_feels_home`** (e.g. `git@github.com:vcrosby22/where_cursor_feels_home.git`) | **Private** |
| **GitHub Pages market report** — static HTML + workflow | **Separate clone** of the report repo (e.g. `financial-reports-upstream/`), *not* the monorepo root | Host/path contains **`financial-reports`** | **Public** |
| **Cursor KB markdown slice** (glossary, triggers, sanitized `cursor-knowledge`) | **`cursor-kb-public/`** after `sync_public_cursor_kb_repo.py` | A **dedicated public repo** — URL must **not** be the private monorepo | **Public** |
| **Dog agent** (if nested git) | **`dog-agent/`** | That project’s own remote (typically **private**) | Usually **private** |

**Do not**

- Push the **monorepo root** to **`financial-reports`** — the report repo only gets **ported** artifacts per **`financial-agent/PORTING.md`** / **`financial-agent/PUBLISHING.md`**.
- Point **`cursor-kb-public/`**’s `origin` at **`where_cursor_feels_home`** — the export is **gitignored** in the private repo *on purpose*; it should be its **own** public remote.
- Copy **`BACKLOG*.md`**, **`journal/`**, or **`.env`** into a **public** repo or handbook tree without an explicit sanitization pass (see checklist below).

**Agent habit:** When helping Victoria **commit + push**, name **which repo** you are pushing to (private workspace vs public report vs public KB). If `origin` does not match the table for the current directory, **stop** and fix the remote before pushing.

---

## Mechanics

### Option A — Two repos (recommended)

1. **Private:** full monorepo (current setup).  
2. **Public:** small repo (e.g. `cursor-knowledge` template pattern) with only approved paths — copy or subtree export; **never** copy `BACKLOG*.md`, `BACKLOG_INBOX.md`, `journal/`, `profile/` unless intentionally sanitized.

### Option B — Same repo, visibility

- **Private repo** is the default for this workspace (`BL-05` pattern).  
- Do **not** flip the whole repo **public** without a full audit (see [cursor-knowledge README](../../cursor-knowledge/README.md)).

### Option C — Public HTML only (no new Git repo)

```bash
python3 scripts/sync_workspace_handbook.py --public
mkdocs build -f mkdocs.public.yml
```

Uses **`mkdocs.public.yml`** at the **repository root** (nav **without** workspace backlog + inbox pages). Upload `site/` to static hosting only after spot-checking generated HTML.

### Option D — Public Markdown slice repo (`cursor-kb-public/`)

For a **small public Git repo** of Markdown sources (not HTML), run:

```bash
python3 scripts/sync_public_cursor_kb_repo.py
```

That writes **`cursor-kb-public/`** at the monorepo root with **GLOSSARY**, **triggers cheatsheet** (+ linked guides), **`cursor-knowledge/*.md`**, and **copies of `.cursor/commands/*.md`** plus **`non-technical-documentation`** as a `.md` file. The folder is **gitignored** in the private repo so you **`cd cursor-kb-public`**, **`git init`**, and push to a **separate** public remote. See the generated **`README.md`** inside that folder for the exact layout.

---

## Checklist before “public”

- [ ] No `BACKLOG.md` / `BACKLOG_STORY_DETAILS` / `BACKLOG_INBOX` / `backlog/` in the **public** artifact.  
- [ ] No `journal/` paths.  
- [ ] No `.env` or secrets (run `git diff`, search for keys).  
- [ ] `PROJECT_CONTEXT` / `activeContext` reviewed if included.  
- [ ] Triggers cheatsheet and command copies contain **no** private paths you care about (they point at generic workflows).

---

## Changelog

- **2026-03-20** — Initial policy: triggers cheatsheet public-friendly; canonical backlog private; handbook `--public` + `mkdocs.public.yml`; Option D `sync_public_cursor_kb_repo.py` + `cursor-kb-public/`.
- **2026-03-20** — **Where to push (routing)** table — verify `origin` + working directory before every push (private monorepo vs `financial-reports` vs `cursor-kb-public`).
