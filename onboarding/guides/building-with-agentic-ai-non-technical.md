# Building with agentic AI (non-technical)

## At a glance

=== "Beginner"

    You don't need to learn to code. You're learning to **work with an AI assistant** to get things done — outlines, feedback, drafts, landing pages, research. Think of the AI as a fast intern: it needs a goal, constraints, and your review. This guide covers the mindset, safety basics, and first prompts to try.

=== "Intermediate"

    Agentic AI in Cursor means the assistant can read your project files, propose or apply edits, and chain multiple steps. Key concepts: **Plan mode** (think together, review before changes) vs. **Agent mode** (assistant executes directly). Safety: never paste secrets; verify outputs on money/health/legal; use diffs and undo. Custom slash commands extend the workflow.

=== "Advanced"

    This guide covers the product-owner mental model for agentic AI collaboration: defining "done" as acceptance criteria, iteration as the normal workflow (not a failure mode), and the Plan/Agent mode distinction as a trust-gradient control. For deeper technical treatment of how agents work under the hood, see [agentic AI](../../ai-engineering/agentic-ai.md).

---

**You are not “learning to code” first.** You are learning to **collaborate** with an AI assistant inside a tool (Cursor) so you can move product ideas forward: clearer specs, better copy, structured research, simple web pages, and prototypes — at a pace that would be painful alone.

---

## 1. Mindset: you own the outcome

- **You are the product owner.** The assistant is like a **fast, tireless intern**: it needs a **goal**, **constraints**, and **boundaries** (“do not change X”, “keep this under one page”, “ask before spending money”).
- **Outcomes over syntax.** You do not need to memorize commands. You *do* need to say **what “done” looks like** (“a bullet list of user stories”, “feedback on this pitch”, “a landing page section in plain HTML”).
- **Iteration is normal.** First draft → your edits → “tighten this” → repeat. That is how professionals use these tools.

---

## 2. Safety and trust

- **Never paste secrets** into chat: passwords, API keys, bank or health data, confidential client material. If it happened by mistake, **rotate/revoke** the credential.
- **Verify important outputs** — especially anything touching **money, health, legal, or compliance**. The assistant can sound confident and still be wrong.
- **You approve changes.** In Agent mode the tool may edit files; use **diffs** (before/after) and **undo** when something looks off.

---

## 3. Cursor basics (minimal jargon)

| Idea | What it means for you |
|------|------------------------|
| **Chat** | You type goals and questions; the assistant replies and can read files you allow. |
| **Project / folder** | Cursor works best when you **open a folder** (even a small one with a few notes or a simple site). |
| **Plan vs Agent** | **Plan** = think together, review, **no** (or minimal) file changes until you agree. **Agent** = the assistant can **edit files** and **run allowed steps** to implement what you asked. |
| **New chat** | Long chats get summarized and **lose detail**. Start fresh for a new topic and paste a **short handoff** (see [working-with-ai-context.md](working-with-ai-context.md)). |

If your workspace uses a **`[Build]` / `[Discussion]`** label in chat, that is just a signal: **Build** = the turn changed something in the project; **Discussion** = read-only talk. (Common in advanced setups; optional for you.)

---

## 4. First wins (try these before the terminal)

Use your own words; examples below are patterns, not magic phrases.

| Goal | Example prompt shape |
|------|----------------------|
| Clarify an idea | “Critique this product idea. What are the top 3 risks and 3 questions I should answer next?” |
| Structure work | “Turn these messy notes into a one-page outline with: problem, audience, success metric, next steps.” |
| Product language | “Rewrite this for a non-technical reader. Keep tone friendly and cut jargon.” |
| User stories | “From this paragraph, draft 5 user stories in ‘As a … I want … so that …’ form.” |
| Landing copy | “Draft a hero headline, subhead, and three bullets for [describe product]. I will edit tone.” |

Ask for **format** (“table”, “bullets”, “one paragraph”) so the answer fits how you work.

---

## 5. Slash commands (`/`)

Some workspaces define **custom slash commands** (e.g. `/journal`, `/session-end`). They only exist if that workspace ships **`.cursor/commands/`**. In **this** public repo, human-readable summaries live in **[`../reference/slash-commands.md`](../reference/slash-commands.md)** — you can still use the **same ideas** by typing them in plain language (see [cursor-triggers-and-prompts.md](cursor-triggers-and-prompts.md)).

---

## 6. When you are ready for “a real project folder”

1. Open a **small folder** in Cursor (notes, a static site, a doc repo).  
2. Read the **[session playbook](cursor-session-playbook.md)** — terminal tips, GitHub, and how people **hand off context** between chats.  
3. If you need **Git** (save versions, share on GitHub), use **[git-basics-for-non-developers.md](git-basics-for-non-developers.md)**.  
4. If you might publish **public** vs keep **private** work separate, read **[public-vs-private-git-strategy.md](public-vs-private-git-strategy.md)**.

---

## Related

| Topic | Where |
|-------|--------|
| Context and new chats | [working-with-ai-context.md](working-with-ai-context.md) |
| Session playbook (deeper) | [cursor-session-playbook.md](cursor-session-playbook.md) |
| Triggers and phrases | [cursor-triggers-and-prompts.md](cursor-triggers-and-prompts.md) |
| First-week checklist | [../checklists/first-week-cursor-non-technical.md](../checklists/first-week-cursor-non-technical.md) |
| Full catalog | [../INDEX.md](../INDEX.md) |
