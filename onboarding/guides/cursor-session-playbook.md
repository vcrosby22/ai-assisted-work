# Cursor & agentic workflow — session playbook (v1)

**For:** People using Cursor with an AI collaborator inside a **project folder** — including PMs and newcomers who are ready for terminal, Git, or static-site steps.

**New to agentic AI or non-technical?** Read **[Building with agentic AI (non-technical)](building-with-agentic-ai-non-technical.md)** and **[Working with AI context](working-with-ai-context.md)** first; this playbook goes deeper on **implementation** habits.

**Source:** Distilled from workspace sessions (sanitized — **no** tokens or secrets).

---

## 1. Plan mode vs Agent mode

| Mode | Intent |
|------|--------|
| **Plan** | Discuss, design, review — **avoid** changing the repo until you explicitly move to Agent mode or ask for execution. |
| **Agent** | Implement: edits, new files, mutating terminal commands. |

**Trust:** Ground truth = **file diffs** and **terminal output**, not only the assistant’s wording. Your workspace may also use a **`[Build]` / `[Discussion]`** prefix convention (see `.cursor/rules/agent-mode-signal.mdc`).

---

## 2. Terminal hygiene

- Type **one command per line** after the shell prompt (`%`). Press **Enter** once.
- **Avoid** pasting chat **transcripts**, **fake prompts** (`… user@host %`), or **Unicode ellipsis** (`…`) into the shell — they cause `zsh` parse errors or `bquote>` stuck states. **Ctrl+C** escapes continuations.
- **GitHub HTTPS:** Prefer **`gh auth login`** then **`gh auth setup-git`** so Git uses the CLI session. Your Git password is **not** your GitHub web password; use a **PAT** only if Git still prompts — and **never** paste tokens into chat or at the shell as a “command.”
- If **`mkdir ~/.config/gh: permission denied`**, check **`ls -ld ~/.config`** — if owned by **root**, fix with **`sudo chown -R "$(whoami)":staff ~/.config`** (macOS).

---

## 3. Static sites (e.g. GitHub Pages)

- **HTML** built in CI reflects **last successful workflow** — not a live API between runs.
- Separate **data as-of** (what prices/macro **represent**) from **snapshot generated** (when HTML was built). See `financial-agent/PUBLISHING.md` and public report UX patterns.
- **Push** to the **deploy repo** uses **your** credentials; cloud agents may not have your GitHub identity.

---

## 4. Context handoff between chats

Long threads get summarized or truncated. **Don’t rely** on infinite chat memory.

- Update **`activeContext.md`** and today’s **`journal/`** when stopping.
- Start a **new chat** for a new topic after a quick handoff — attach **`@activeContext.md`** or **`@BACKLOG.md`** as needed.

---

## 5. Journaling & backlog signals

- Daily journal template includes **`Backlog candidates (from this session)`** — drafted at **`/session-end`** or substantive wrap-ups (**this chat only** unless you paste more).
- **`BACKLOG.md`** (repo root) holds **prioritized** cross-session items (see backlog rules).
- **Not automatic:** scanning *all* past Cursor threads requires **opt-in** transcript access or a **local script** — not default agent behavior.

---

## 6. Security

- Never commit **`.env`**, PATs, or API keys.
- **Revoke** any token that was pasted into chat or logs.

---

## Related in this repo

- `PROJECT_CONTEXT.md`, `PRIMARY_OBJECTIVES.md`
- `cursor-knowledge/BACKLOG_PHILOSOPHY.md`
- `.cursor/skills/session-backlog-scan/SKILL.md`
- `.cursor/skills/website-qa/SKILL.md` (pre-share QA for the market report site)

*Revise this playbook as you learn — v1 is a starting point for publication.*
