# Enable “auto-scan” of past Cursor chats (BL-10)

**What this is:** A **local**, **opt-in** script that reads Cursor **`agent-transcripts`** (`*.jsonl`) and writes a **draft Markdown report** of lines that look like todos / follow-ups / deferred work. **You review** the report and manually promote items to **`BACKLOG.md`** or your journal — nothing is auto-merged.

**What this is not:** The assistant does **not** silently read all your old chats during normal turns. That would mix privacy, noise, and trust. See `.cursor/skills/session-backlog-scan/SKILL.md` (this thread only unless you authorize).

---

## 1. Prerequisites

- **Python 3.9+** on your machine.
- **Cursor** has stored transcripts for this workspace. Typical path on your Mac for *this* repo:

  `~/.cursor/projects/Users-victoriacrosby-Desktop-Cursor/agent-transcripts/`

  Each subfolder is a chat UUID; inside is one `*.jsonl` file.

- **Trust:** Transcripts can include **API keys, personal info, or work secrets**. Scrub before sharing. Output defaults to **`scratch/transcript-backlog-scans/`** (gitignored).

---

## 2. Run the scanner

From the **workspace root** (`Cursor/`):

```bash
# Default root: ~/.cursor/projects/Users-victoriacrosby-Desktop-Cursor/agent-transcripts
python3 scripts/scan_cursor_transcripts_for_backlog.py
```

**Another project:**

```bash
export CURSOR_AGENT_TRANSCRIPTS_ROOT="$HOME/.cursor/projects/OTHER-PROJECT/agent-transcripts"
python3 scripts/scan_cursor_transcripts_for_backlog.py
```

**Include assistant turns** (noisier — catches “Want me to…?” style text):

```bash
python3 scripts/scan_cursor_transcripts_for_backlog.py --include-assistant
```

**Custom output path:**

```bash
python3 scripts/scan_cursor_transcripts_for_backlog.py --out /tmp/my-scan.md
```

Open the generated **`scratch/transcript-backlog-scans/scan-*.md`**, delete false positives, then:

- Paste survivors under **`Backlog candidates`** in today’s journal, **or**
- Add **`BL-##`** rows to **`BACKLOG.md`** (`a2b` + **`BACKLOG_STORY_DETAILS.md`**).

---

## 3. Semi-automation (optional)

- **Weekly Review:** Run the script Sunday, spend 10 minutes triaging.
- **Cron / `launchd`:** Schedule the same command; still **human-in-the-loop** for promotion.
- **Tuning:** Edit trigger regex in **`scripts/scan_cursor_transcripts_for_backlog.py`** if you get too much / too little noise.

---

## 4. Having the *agent* use transcripts

Only after you **explicitly authorize** in chat, e.g.:

> You may read `scratch/transcript-backlog-scans/scan-….md` and propose journal/BL rows.

Or paste excerpts yourself. **Do not** point the agent at raw `~/.cursor/.../agent-transcripts` unless you accept the **privacy** risk in that thread.

---

## 5. Relation to other capture

| Mechanism | Scope |
|-----------|--------|
| **`session-backlog-scan`** skill + **`/session-end`** | **This chat** → journal `Backlog candidates` |
| **This script** | **All chats** on disk for this project → draft report |
| **`BACKLOG.md`** | Canonical prioritized todo list after you promote |

---

*See also:* [`working-with-ai-context.md`](working-with-ai-context.md) · **[`../../scripts/scan_cursor_transcripts_for_backlog.py`](../../../scripts/scan_cursor_transcripts_for_backlog.py)**
