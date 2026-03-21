# Catalog — full workspace only

**Read this if** your clone is **not** the minimal public [`cursor-knowledge`](https://github.com/vcrosby22/cursor-knowledge) tree but a **larger workspace** that includes `BACKLOG.md`, `scripts/`, `.cursor/commands/`, `.cursor/skills/`, `BACKLOG_INBOX.md`, etc.

The main **[`INDEX.md`](INDEX.md)** lists only artifacts whose links work on a **standalone public clone**. Below are the **extra** entries and paths that assume that fuller layout.

---

## Extra artifacts (typical paths)

| Artifact | Typical location | Notes |
|----------|------------------|--------|
| HTML handbook (browse KB in browser) | `scripts/README-workspace-handbook.md` | `sync_workspace_handbook.py` + `mkdocs build` → `site/` |
| Transcript backlog scan | `scripts/scan_cursor_transcripts_for_backlog.py` + [`guides/enable-transcript-backlog-scan.md`](guides/enable-transcript-backlog-scan.md) | Opt-in local scan of `agent-transcripts` |
| Idea inbox + `/capture-idea` | `BACKLOG_INBOX.md`, `.cursor/commands/capture-idea.md`, skill `backlog-inbox-capture` | Mid-task idea capture |
| Slash command **definitions** (machine) | `.cursor/commands/*.md` | Human summaries: [`reference/slash-commands.md`](reference/slash-commands.md) |
| Rules | `.cursor/rules/*.mdc` | e.g. backlog prioritization, agent mode signal, journaling |
| Skills | `.cursor/skills/*/SKILL.md` | e.g. `session-backlog-scan`, `backlog-inbox-capture`, `website-qa` |
| Prioritized backlog | `BACKLOG.md`, `BACKLOG_STORY_DETAILS.md` | Canonical cross-session work |
| Glossary promotion rules | e.g. `non-technical-documentation.mdc` | Controlled vocabulary for `product-management/GLOSSARY.md` |

---

## Publication reminder

Policy: **[Public vs private Git strategy](guides/public-vs-private-git-strategy.md)** — keep **canonical backlog** and private journals **private**; triggers and onboarding copy can be **public-safe**.

---

Back to **[`INDEX.md`](INDEX.md)** for the full public catalog.
