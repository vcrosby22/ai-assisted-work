# Terms & definitions (non-developer onboarding)

**Audience:** Readers who are **not** professional developers but who use **AI assistants**, **software products**, and **technical workflows** (e.g. Cursor, GitHub, configs, data tools). Definitions favor **plain language** over precision-for-engineers.

**How this relates to other docs**

| Doc | Role |
|-----|------|
| This file | **Short definitions** of concepts, acronyms, and stack words you’ll see in this workspace. |
| [`PM_KNOWLEDGE.md`](PM_KNOWLEDGE.md) | Deeper PM/framework notes; **§6** includes workspace-captured strategy vocabulary (e.g. defensibility in context). |
| [`onboarding/`](../onboarding/) | How to *use* Cursor, git, and workflows step by step. |

**How entries grow:** Session **Glossary candidates** (journal or `/session-end`) are drafts. Promote a row here when a term **recurs** or **confused someone** — keep definitions **stable** and **one sentence** when possible.

**Persona note:** We use one **default reader** (“confident learner, not coding-native”) instead of multiple fictional personas unless a doc truly serves *contrasting* audiences (e.g. exec vs implementer). That keeps tone consistent without extra ceremony.

---

## How terms relate to goals (user-centered)

**North-star outcome for this sheet:** A non-developer can use **AI-assisted tools and this repository** with confidence — definitions match **jobs readers are trying to do**, not only internal engineering labels.

**Layers (for reading and future filtering):**

1. **Parent outcome (Category)** — stable label below; use the **same string** in every row’s **Category** column so a future UI or export can **filter** (“show me only GitHub-related terms”).
2. **Section** in this file (e.g. *Git & GitHub essentials*) — how humans skim; **not** the same as a backlog Epic name.
3. **Term** — one row; a term may conceptually support more than one outcome, but we assign a **single primary Category** per row to keep the sheet sortable.

**Backlog vs glossary:** **[`BACKLOG.md`](../../BACKLOG.md) Epics** track **delivery** of work. This sheet tracks **reader vocabulary**. Ongoing structure and harvest: **BL-29** (Onboarding epic).

### Controlled vocabulary — Parent outcome (Category)

Use **only** these labels in the **Category** column:

| Category (exact string) | Reader job |
|-------------------------|------------|
| **Work effectively with AI in Cursor** | Rules, skills, chat limits, workspace files like `activeContext.md`, backlog IDs |
| **Ship and sync changes with GitHub** | Version control, PRs, Actions, Pages, CI/CD |
| **Understand product and delivery language** | Strategy, prioritization, MVP-style product vocabulary |
| **Use configs, files, and the web safely** | Formats, secrets, HTTP, static sites, APIs as a user |
| **Read market and investing reports** | Symbols and indicators in this repo’s financial/report context |

### Parent outcome → primary backlog Epic(s)

Many-to-many in real life; this table is **where delivery attention usually sits** when we improve that area.

| Parent outcome (Category) | Primary Epic(s) (see `BACKLOG.md`) |
|---------------------------|-------------------------------------|
| **Work effectively with AI in Cursor** | Collaboration & Cursor workflow; AI skills; Foundational AI knowledge |
| **Ship and sync changes with GitHub** | Traditional technical foundations; Shipping & spin-outs |
| **Understand product and delivery language** | Product management (PM) |
| **Use configs, files, and the web safely** | Traditional technical foundations |
| **Read market and investing reports** | Shipping & spin-outs (e.g. public report); financial-agent work |

---

## Core concepts

| Term | Category (Parent outcome) | Plain definition | See also |
|------|---------------------------|------------------|----------|
| **Durable documentation** (durable docs) | Work effectively with AI in Cursor | Files **in the repo** (or otherwise versioned) that stay **findable and editable** across sessions — the **ledger** for decisions, vocabulary, and how-tos. **Chat** can be compacted or lost; durable docs are what you **@‑reference** as **source of truth**. | [`working-with-ai-context.md`](../onboarding/guides/working-with-ai-context.md) §4; `.cursor/rules/non-technical-documentation.mdc` |
| **Defensibility** (product strategy) | Understand product and delivery language | How hard it is for a competitor to **copy your product** and take your **users or profit** after you’ve shown the idea works. *Not* the same as “secure against hackers” — that’s **security** or **attack surface**. | [`PM_KNOWLEDGE.md`](PM_KNOWLEDGE.md) §6.2 |
| **Time to first user** | Understand product and delivery language | How quickly you can put a **small real version** in front of someone who actually cares (not how polished the vision is). | [`PM_KNOWLEDGE.md`](PM_KNOWLEDGE.md) §6.3 |
| **Personal itch** | Understand product and delivery language | Building something **you** keep wanting to use or fix — a sanity check for stamina through boring implementation work. | [`PM_KNOWLEDGE.md`](PM_KNOWLEDGE.md) §6.3 |
| **Compaction** (AI chat) | Work effectively with AI in Cursor | When the product **summarizes or trims** older messages so the model fits in its context window — themes survive, **exact wording and paths** may not. | [`working-with-ai-context.md`](../onboarding/guides/working-with-ai-context.md) |
| **Lost in the middle** | Work effectively with AI in Cursor | Research observation: models often **underweight facts** buried in a **long middle** of text; put critical facts at **start/end** or in **repo files**. | Same guide + [`AGENTIC_CONTEXT_URLS.md`](../cursor-knowledge/AGENTIC_CONTEXT_URLS.md) |

## This workspace & Cursor

Terms that show up in **`PROJECT_CONTEXT.md`**, **journals**, and **`onboarding/`** when working in this repo.

| Term | Category (Parent outcome) | Plain definition |
|------|---------------------------|------------------|
| **Workspace** | Work effectively with AI in Cursor | The **project folder** you opened in Cursor (this repo is one workspace). |
| **Plan mode vs Agent mode** | Work effectively with AI in Cursor | **Plan** = discuss without auto-editing the repo; **Agent** = the assistant may **edit files** and run commands. *Playbook:* [`cursor-session-playbook.md`](../onboarding/guides/cursor-session-playbook.md). |
| **`[Build]` / `[Discussion]`** | Work effectively with AI in Cursor | In-chat labels: **Build** = this turn **changes** files or runs mutating commands; **Discussion** = read-only. *Rule:* `.cursor/rules/agent-mode-signal.mdc`. |
| **Rule** (Cursor) | Work effectively with AI in Cursor | A file under **`.cursor/rules/`** with instructions the agent should **follow repeatedly** (like a style guide for AI). |
| **Skill** | Work effectively with AI in Cursor | A **`SKILL.md`** under **`.cursor/skills/`** the agent **reads when relevant** — a packaged workflow or domain brief. |
| **Slash command** | Work effectively with AI in Cursor | A **`/name`** workflow defined under **`.cursor/commands/`** (e.g. **`/journal`**, **`/session-end`**). |
| **Hook** | Work effectively with AI in Cursor | Optional **event-driven** step (e.g. after save) configured in **`.cursor/hooks`** — not “hooks” in the business sense. |
| **`activeContext.md`** | Work effectively with AI in Cursor | Short **“where we left off”** file at the repo root for the **next** session or chat. |
| **`BACKLOG.md`** | Work effectively with AI in Cursor | The **single prioritized** cross-session todo list for this repo (rows like **BL-##**). |
| **BL-##** | Work effectively with AI in Cursor | **Backlog ID** — one row in `BACKLOG.md`; details may live in **`BACKLOG_STORY_DETAILS.md`**. |
| **Epic** | Work effectively with AI in Cursor | A **theme** grouping backlog items (e.g. Onboarding, Financial agent). |
| **Token** (AI context) | Work effectively with AI in Cursor | A **chunk of text** the model can attend to; long chats hit **limits**, so big pastes cost **attention budget**. Not the same as an **API key**. |

## Git & GitHub essentials

| Term | Category (Parent outcome) | Plain definition |
|------|---------------------------|------------------|
| **Git** | Ship and sync changes with GitHub | **Version control** on your computer — snapshots (**commits**) of files over time. |
| **GitHub** | Ship and sync changes with GitHub | **Hosting** for Git repos online — backup, collaboration, **Actions**, **Pages**. |
| **Clone** | Ship and sync changes with GitHub | **Download** a copy of a repo (first time). |
| **Commit** | Ship and sync changes with GitHub | **Save a snapshot** locally with a message. |
| **Push** | Ship and sync changes with GitHub | **Upload** your commits to GitHub. |
| **Pull** | Ship and sync changes with GitHub | **Download** others’ (or your) latest commits from GitHub. |
| **Branch** | Ship and sync changes with GitHub | A **parallel line** of changes; **`main`** is usually the primary line. |
| **Remote** | Ship and sync changes with GitHub | The **GitHub-side** copy of the repo (often named **`origin`**). |
| **SHA / commit hash** | Ship and sync changes with GitHub | Short **unique ID** for one commit (e.g. `c6de212`). |
| **GitHub Actions** | Ship and sync changes with GitHub | **Automated jobs** on GitHub (e.g. build HTML on a schedule or after a push). |
| **GitHub Pages** | Ship and sync changes with GitHub | Serves a **static website** from a repo branch or folder (common for reports). |
| **CI / CD** | Ship and sync changes with GitHub | **Continuous integration** = auto test/build on change; **continuous delivery** = auto **ship** closer to production. Often used loosely for “Actions ran green.” |
| **PAT** | Ship and sync changes with GitHub | **Personal access token** — a **long password-like secret** for GitHub API/Git over HTTPS; **never** paste into chat or commit. Prefer **`gh auth login`**. |

*Step-by-step:* [`onboarding/guides/git-basics-for-non-developers.md`](../onboarding/guides/git-basics-for-non-developers.md)

## Config, files & the web

| Term | Category (Parent outcome) | Plain definition |
|------|---------------------------|------------------|
| **YAML** | Use configs, files, and the web safely | A **readable config** format using indentation (many **`config.yaml`** files). |
| **JSON** | Use configs, files, and the web safely | A structured **data exchange** format with `{` `}` and `"quotes"` — common for APIs and configs. |
| **`.env`** | Use configs, files, and the web safely | A **local secrets** file (API keys); **never commit** it — see **`.env.example`** for **names only**. |
| **SQLite** | Use configs, files, and the web safely | A **single-file database** (no separate server) — used by some tools in this repo. |
| **HTTP / HTTPS** | Use configs, files, and the web safely | **Web request** protocol; **S** = encrypted (padlock in the browser). |
| **Static site / HTML report** | Use configs, files, and the web safely | **Pre-built files** served as-is (e.g. GitHub Pages) — **not** a live app talking to a database on each view. |
| **URL** | Use configs, files, and the web safely | **Web address** (link) to a page or API. |

## Product & delivery shorthand

One-line pointers; detail in **`PM_KNOWLEDGE.md`**.

| Term | Category (Parent outcome) | Expands / means | Plain definition |
|------|---------------------------|-----------------|------------------|
| **OKR** | Understand product and delivery language | Objectives and key results | **Directional goal** + a few **measurable** outcomes (often quarterly). |
| **RICE** | Understand product and delivery language | Reach, Impact, Confidence, Effort | A **scoring** formula to compare ideas; still needs judgment. |

## Acronyms & stack vocabulary

| Term | Category (Parent outcome) | Expands / means | Plain definition |
|------|---------------------------|-----------------|------------------|
| **AI** | Work effectively with AI in Cursor | Artificial intelligence | Software that **learns patterns** from data or examples; in chat tools, often means “model that generates text or suggestions.” |
| **API** | Use configs, files, and the web safely | Application programming interface | A **structured way programs talk to each other** (like a menu of requests a server understands). You don’t need to build one to *use* tools that mention APIs. |
| **CLI** | Use configs, files, and the web safely | Command-line interface | Typing **text commands** in a terminal instead of clicking buttons; many dev tools expose a CLI for automation. |
| **LLM** | Work effectively with AI in Cursor | Large language model | The **text-prediction engine** behind assistants like ChatGPT / Claude; good at language, can be wrong (“hallucinate”). |
| **Markdown** | Work effectively with AI in Cursor | — | Simple text formatting (`#` headings, `-` lists); common for READMEs and journals in repos. |
| **MVP** | Understand product and delivery language | Minimum viable product | The **smallest thing** you can ship to **learn** whether you’re solving a real problem. |
| **PWA** | Understand product and delivery language | Progressive web app | A **website** that can feel app-like (offline bits, install prompt); one way to ship without app stores. |
| **PR** | Ship and sync changes with GitHub | Pull request | On GitHub: “**please merge** my proposed changes” — a reviewable package of edits. |
| **repo** | Ship and sync changes with GitHub | Repository | A **folder of project files** + its history, usually managed with **git**. |
| **HTML** | Use configs, files, and the web safely | HyperText Markup Language | The **markup** browsers render into web pages; **static HTML** = saved file, not generated live per click. |
| **ETF** | Read market and investing reports | Exchange-traded fund | A **basket** of stocks/bonds you buy like one ticker — used in journals for **sector/market** coverage. |
| **FRED** | Read market and investing reports | Federal Reserve Economic Data | **Free economic data** API (St. Louis Fed) — referenced in **financial-agent** / macro discussions. |

---

## Optional: financial-report jargon

Only if you’re reading **market-report** or **financial-agent** notes; not general PM vocabulary.

| Term | Category (Parent outcome) | Plain definition |
|------|---------------------------|------------------|
| **Ticker** | Read market and investing reports | **Stock/ETF symbol** (e.g. `AAPL`, `XLK`). |
| **VIX** | Read market and investing reports | **Volatility index** — often called the “fear gauge”; high ≠ direction, it’s **expected wobble**. |
| **RSI** | Read market and investing reports | **Relative strength index** — a **0–100** momentum-style indicator; “overbought/oversold” labels are **heuristic**. |

---

## Changelog

- **2026-03-20** — **BL-29:** **Durable documentation** defined; **user-centered IA**; **Category (Parent outcome)** column on all tables; **Epic mapping**; controlled vocabulary for future filtering.
- **2026-03-20** — Expanded from **journals** (2026 W12), **`onboarding/guides`**, **`PROJECT_CONTEXT.md`**, **`cursor-session-playbook`**: Cursor/workspace tokens, GitHub Actions/Pages, compaction, YAML/`.env`, OKR/RICE one-liners, optional market-report terms.
- **2026-03-20** — Initial sheet; defensibility + choice lenses + common acronyms for non-developer readers.
