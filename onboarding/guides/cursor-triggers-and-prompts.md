# Cursor triggers & prompts — cheatsheet

**One bookmark** for slash commands, natural phrases, and where behavior lives in this repo.  
Sanitized — **no** secrets, tokens, or API keys.

**Publication:** This guide is **intended to be public-safe**. Canonical **backlog files** are **private** — see [Public vs private Git strategy](public-vs-private-git-strategy.md).

---

## Slash commands (`/`)

Type in Cursor chat. Definitions live in [`.cursor/commands/`](../../../.cursor/commands/).

| Command | When to use | Definition file |
|---------|-------------|-----------------|
| **`/journal`** | Create or update **today’s journal**; substantive sessions may also draft **Backlog candidates** and **Glossary candidates**. | [`journal.md`](../../../.cursor/commands/journal.md) |
| **`/session-end`** | **Wrap the session:** journal sections, **Backlog candidates**, **Glossary candidates**, `activeContext.md`, optional `CURSOR_KNOWLEDGE.md`. | [`session-end.md`](../../../.cursor/commands/session-end.md) |
| **`/pm`** | **Product management** context — discovery, prioritization, roadmaps, AI product risks; reads `product-management/PM_KNOWLEDGE.md`. | [`pm.md`](../../../.cursor/commands/pm.md) |
| **`/pmo`** | **PMO / delivery** context — Agile, Lean, Six Sigma, CRISP-DM; reads `pmo/PMO_KNOWLEDGE.md`. | [`pmo.md`](../../../.cursor/commands/pmo.md) |
| **`/capture-idea`** | **Park an idea** mid-build into [`BACKLOG_INBOX.md`](../../../BACKLOG_INBOX.md) without derailing the task. | [`capture-idea.md`](../../../.cursor/commands/capture-idea.md) |
| **`/canine`** | **Dog / puppy** behavior and welfare (uses `dog-agent` stack when present). | [`canine.md`](../../../.cursor/commands/canine.md) |
| **`/collaboration-check`** | **Collaboration health** between you and the agent. | [`collaboration-check.md`](../../../.cursor/commands/collaboration-check.md) |

---

## Natural phrases (no slash)

The assistant may follow **rules** and **skills** when you say things like:

| You say (examples) | What it routes to |
|--------------------|-------------------|
| **“Journal this”** / **“add to journal”** | Today’s journal file; same conventions as `/journal`. |
| **“Session end”** / **“wrap up”** | Same checklist as **`/session-end`** (journal, backlog scan, glossary scan, `activeContext`). |
| **“Glossary this session”** / **“capture terms”** | Skill [`non-technical-glossary-capture`](../../../.cursor/skills/non-technical-glossary-capture/SKILL.md) → **`Glossary candidates`** in the journal; promote to [`GLOSSARY.md`](../../product-management/GLOSSARY.md) when stable (**include Category** per controlled vocabulary). |
| **“Backlog candidates”** / **“scan this chat for backlog”** | Skill [`session-backlog-scan`](../../../.cursor/skills/session-backlog-scan/SKILL.md) → journal **Backlog candidates**. |
| **“Use the PM skill”** / **“/pm”** | `product-management` skill + `PM_KNOWLEDGE.md`. |
| **“Park this idea”** / **“capture idea”** | `BACKLOG_INBOX.md` + [`backlog-inbox-capture`](../../../.cursor/skills/backlog-inbox-capture/SKILL.md) skill. |

---

## Glossary flow (reminder)

1. **`/session-end`** or **`/journal`** (substantive) → draft **`Glossary candidates (from this session)`** in today’s journal.  
2. Assistant asks before **bulk-editing** [`product-management/GLOSSARY.md`](../../product-management/GLOSSARY.md).  
3. Rules: [`non-technical-documentation.mdc`](../../../.cursor/rules/non-technical-documentation.mdc), skill above.

---

## Plan vs Agent

| Mode | Intent |
|------|--------|
| **Plan** | Discuss and design; **avoid** repo edits until you switch to Agent or ask for execution. |
| **Agent** | Implement: files, mutating terminal commands. |

Details: [`cursor-session-playbook.md`](cursor-session-playbook.md). Turn labels: **[Build]** vs **[Discussion]** in chat (see `agent-mode-signal` rule).

---

## Stable context for new chats

Long threads **lose detail** (compaction). For **contracts** (decisions, paths, backlog):

- Attach **`@activeContext.md`**, **`@BACKLOG.md`**, or other repo files.  
- Deep dive: [`working-with-ai-context.md`](working-with-ai-context.md).

---

## Related

| Topic | Where |
|-------|--------|
| Onboarding catalog | [`../INDEX.md`](../INDEX.md) |
| Session playbook | [`cursor-session-playbook.md`](cursor-session-playbook.md) |
| Terms sheet | [`../../product-management/GLOSSARY.md`](../../product-management/GLOSSARY.md) |
| Build HTML handbook | [`../../scripts/README-workspace-handbook.md`](../../../scripts/README-workspace-handbook.md) |
