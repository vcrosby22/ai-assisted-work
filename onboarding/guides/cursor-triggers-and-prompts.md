# Cursor triggers & prompts — cheatsheet

**One bookmark** for slash commands, natural phrases, and how behavior maps to your workspace.  
Sanitized — **no** secrets, tokens, or API keys.

**Publication:** This guide is **intended to be public-safe**. Canonical **backlog files** in full workspaces are often **private** — see [Public vs private Git strategy](public-vs-private-git-strategy.md).

---

## Slash commands (`/`)

Type in Cursor chat when your project defines them under **`.cursor/commands/`**. On a bare clone of this repo those files are **not** shipped; use the in-repo summary instead:

**Human-readable summaries:** [`../reference/slash-commands.md`](../reference/slash-commands.md)

**Full workspace** (paths on disk): see [`../INDEX-full-workspace-only.md`](../INDEX-full-workspace-only.md).

---

## Natural phrases (no slash)

In a workspace with **rules** and **skills**, the assistant may still respond to plain language:

| You say (examples) | What it routes to |
|--------------------|-------------------|
| **“Journal this”** / **“add to journal”** | Same idea as **`/journal`** — today’s journal file when that workflow exists. |
| **“Session end”** / **“wrap up”** | Same checklist as **`/session-end`** when configured (journal, backlog scan, glossary scan, `activeContext`). |
| **“Glossary this session”** / **“capture terms”** | Draft **Glossary candidates** in the journal; promote to [`product-management/GLOSSARY.md`](../../product-management/GLOSSARY.md) when stable. |
| **“Backlog candidates”** / **“scan this chat for backlog”** | Draft **Backlog candidates** in the journal (skill-driven in full workspaces). |
| **“Use the PM skill”** / **“/pm”** | `product-management` context + `PM_KNOWLEDGE.md` when present. |
| **“Park this idea”** / **“capture idea”** | Append to **`BACKLOG_INBOX.md`** when that file exists (full workspace). |

Skill file paths (`.cursor/skills/...`) live only in **full** workspaces — see [`../INDEX-full-workspace-only.md`](../INDEX-full-workspace-only.md).

---

## Glossary flow (reminder)

1. **`/session-end`** or **`/journal`** (substantive) → draft **`Glossary candidates (from this session)`** in today’s journal — when those commands exist.  
2. Assistant should ask before **bulk-editing** [`product-management/GLOSSARY.md`](../../product-management/GLOSSARY.md).  
3. Controlled vocabulary and promotion rules may live in **`.cursor/rules/`** in a full workspace.

---

## Plan vs Agent

| Mode | Intent |
|------|--------|
| **Plan** | Discuss and design; **avoid** repo edits until you switch to Agent or ask for execution. |
| **Agent** | Implement: files, mutating terminal commands. |

Details: [`cursor-session-playbook.md`](cursor-session-playbook.md). Some workspaces use a **`[Build]`** vs **`[Discussion]`** prefix in chat to signal the same distinction.

---

## Stable context for new chats

Long threads **lose detail** (compaction). For **contracts** (decisions, paths, backlog):

- Attach key files with **`@`** (e.g. `activeContext.md`, `BACKLOG.md`) when they exist in your project.  
- Deep dive: [`working-with-ai-context.md`](working-with-ai-context.md).

---

## Related

| Topic | Where |
|-------|--------|
| Onboarding catalog | [`../INDEX.md`](../INDEX.md) |
| Full workspace extras | [`../INDEX-full-workspace-only.md`](../INDEX-full-workspace-only.md) |
| Session playbook | [`cursor-session-playbook.md`](cursor-session-playbook.md) |
| Terms sheet | [`../../product-management/GLOSSARY.md`](../../product-management/GLOSSARY.md) |
