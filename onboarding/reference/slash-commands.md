# Slash commands — human-readable reference

Cursor lets a workspace define **slash commands**: you type `/something` in chat and the assistant follows a short recipe. Commands are **optional** and only appear when the project includes **`.cursor/commands/`** (often in a private or team template repo).

This page summarizes common commands from the **where_cursor_feels_home**-style workspace so the onboarding cheatsheet works on a **bare clone** of [`cursor-knowledge`](https://github.com/vcrosby22/cursor-knowledge) (no `.cursor/` folder here).

---

## Commands (summary)

| Command | When to use | What it typically does |
|---------|-------------|-------------------------|
| **`/journal`** | End of day or after a meaningful session | Create or update **today’s journal**; may draft **Backlog candidates** and **Glossary candidates**. |
| **`/session-end`** | You are closing a session | Wrap-up: journal sections, backlog/glossary candidates, update **`activeContext.md`**, optional **`CURSOR_KNOWLEDGE.md`**. |
| **`/pm`** | Product thinking | Load **product management** context — discovery, prioritization, roadmaps, AI product risks; reads **`product-management/PM_KNOWLEDGE.md`** when present. |
| **`/pmo`** | Delivery / process | **PMO** context — Agile, Lean, Six Sigma, CRISP-DM; reads **`pmo/PMO_KNOWLEDGE.md`** when present (not in minimal public tree). |
| **`/capture-idea`** | Mid-task “park this thought” | Append a quick line to **`BACKLOG_INBOX.md`** (or equivalent) without derailing the current build — **only if that file exists**. |
| **`/canine`** | Dog / puppy questions | Behavior and welfare guidance when a **`dog-agent`** (or similar) stack is in the repo. |
| **`/collaboration-check`** | Things feel off with the assistant | Short collaboration health check between you and the agent. |

---

## If you do not have these files

You can still **ask in plain language**: e.g. “Help me wrap up this session: draft journal bullets and open questions from this chat.” See [cursor-triggers-and-prompts.md](../guides/cursor-triggers-and-prompts.md).

---

## Full workspace–only pieces

Backlog inbox, transcript scripts, HTML handbook sync, and skill files are documented in **[`../INDEX-full-workspace-only.md`](../INDEX-full-workspace-only.md)**.
