# Working with AI context (humans + Cursor)

## At a glance

=== "Beginner"

    AI assistants **forget** details in long conversations — they summarize older messages and lose nuance. This guide teaches you when to **start a fresh chat**, how to keep important information **in files** (not just chat), and why your project folder is the AI's most reliable memory.

=== "Intermediate"

    LLMs have a finite context window; long threads get compacted and lose detail. Best practices: keep truth in repo files (not chat), use `activeContext.md` or similar for session state, start fresh threads with a short handoff note, and use rules/skills for persistent instructions that survive across sessions.

=== "Advanced"

    Context window management across the 5-layer architecture: system identity (rules), knowledge retrieval (indexing + RAG), short-term memory (chat + activeContext), long-term memory (knowledge base, journal), and tools. Lost-in-the-middle effect (Liu et al., 2023) means position matters. For the full technical treatment, see [context engineering](../../ai-engineering/context-engineering.md).

---

**Goal:** Decide when to **stay in a long chat**, when to **start fresh**, and how to **keep truth in files** (your project folder) so the agent doesn’t rely only on fragile “conversation memory.” You can use these ideas even when your “repo” is just a few notes — open **any** folder in Cursor as a project.

**Reading list (26 links):** [`cursor-knowledge/ai-context-reading-list.md`](../../cursor-knowledge/ai-context-reading-list.md)

---

## 1. Does coming back to this chat for days still “work”?

**Partly — with caveats.**

- Each time you send a message, the product typically assembles a **bundle of context**: recent messages, attached files, rules, sometimes a **summary** of older thread content if the thread is long.
- **Long threads** often get **compacted / summarized** (see [Anthropic on compaction](https://docs.anthropic.com/en/docs/build-with-claude/compaction)). That preserves *themes* but can drop *exact* wording, file paths, or decisions unless they were saved elsewhere.
- Models also show **recency bias** and **lost-in-the-middle** effects: details at the **start** or **end** of what’s visible tend to be easier to use than facts buried in a huge middle block ([*Lost in the Middle*](https://arxiv.org/abs/2307.03172)).

**So:** Returning to the same chat **can** feel continuous for **days**, especially for vibe and short-term intent — but for **contracts** (decisions, schemas, URLs, “do/don’t”), treat the chat as **unreliable archival storage**.

---

## 2. When is a chat “too much information”?

There isn’t one public number for Cursor that always holds — limits are **token-based** and product-specific. **Symptoms** it’s time to compact or fork:

- The assistant **repeatedly forgets** something you agreed on **earlier in the same thread**.
- It **contradicts** an earlier decision without noticing.
- You waste turns **re-pasting** the same constraints, file paths, or error logs.
- You’re switching **projects** or **mental modes** (e.g. deep debug vs. product planning) in one giant thread.

**Heuristic:** If you’d lose more than ~15 minutes if the chat vanished, **checkpoint into the repo** (see §4).

---

## 3. New chat vs. old chat — practical rules

| Situation | Prefer |
|-----------|--------|
| Same feature, same bug, same files; thread still “coherent” | **Stay**; @-mention key files |
| Long meander; lost track of decisions; lots of failed attempts in history | **New chat** + short **handoff** (below) |
| Sensitive / noisy history you don’t want influencing next steps | **New chat** |
| Teaching the agent a **lasting** behavior | **Rule** or **skill** in `.cursor/`, not more chat |

**Handoff template (paste at top of new chat):**

```text
Continuing work: [one-line goal]
Source of truth: [path(s) — e.g. BACKLOG.md, TICKETING_MODEL.md]
Last decision: [bullet]
Do NOT assume: [bullet]
Next step: [bullet]
```

---

## 4. Put durable context in the workspace (best ROI)

**Principle:** Chat = **scratchpad + execution**; your project folder = **ledger**.

Many **full** workspaces use a pattern like this:

| Mechanism | Holds |
|-----------|--------|
| **`activeContext.md`** | Where we left off **this week** |
| **`.cursor/rules/`** | Stable instructions (Cursor: rules are injected because models **don’t** “remember” between completions the way humans do — see [Cursor Rules docs](https://cursor.com/docs/context/rules)) |
| **`journal/`** | Narrative + decisions |
| **`BACKLOG.md` + `BACKLOG_STORY_DETAILS.md`** | Prioritized work with **descriptions** |
| **`session-log.md` / `cursor-knowledge/`** | Reusable facts and reading lists |

If you only have this **public** knowledge pack, you still have **`cursor-knowledge/`**, **`product-management/`**, and onboarding guides — use **one** note file (e.g. `MY_CONTEXT.md`) as a mini–`activeContext` until you adopt a bigger template. See [onboarding `README`](../README.md) vs [full workspace catalog](../INDEX-full-workspace-only.md).

---

## 5. How to communicate so context “sticks”

1. **Name artifacts:** “Save this as X in path Y” beats “remember that.”  
2. **One intent per message** when possible; long rambles dilute what gets attended to.  
3. **Repeat critical constraints** once per “phase” (after big compaction risk), or pin them in a **rule**.  
4. **@-reference files** instead of pasting huge blobs — the tool layer pulls **current** content.  
5. **Close loops:** “Update `activeContext.md`” / “add BL-##” so the *next* session (or new chat) inherits truth.

---

## 6. For others learning this

Share two files:

1. This guide (**how to behave**).  
2. [`ai-context-reading-list.md`](../../cursor-knowledge/ai-context-reading-list.md) (**why** — 26 sources: papers + vendor docs).

---

*Changelog: 2026-03-25 — Initial version; pairs with ai-context-reading-list.md.*
