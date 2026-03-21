# Onboarding catalog

| Artifact | Location | Status | Notes |
|---------|----------|--------|-------|
| **Public vs private Git** (what to fork / publish) | [`guides/public-vs-private-git-strategy.md`](guides/public-vs-private-git-strategy.md) | Ready (v1) | Triggers **public-safe**; **backlog private**; `mkdocs.public.yml` + `--public` |
| **Cursor triggers & prompts** (slash + phrases) | [`guides/cursor-triggers-and-prompts.md`](guides/cursor-triggers-and-prompts.md) | Ready (v1) | Cheatsheet: `/journal`, glossary capture, Plan vs Agent |
| **HTML handbook** (browse KB in browser) | [`../scripts/README-workspace-handbook.md`](../../scripts/README-workspace-handbook.md) | Ready (v0) | **BL-30:** `sync_workspace_handbook.py` + `mkdocs build` → `site/`; **no journal** in sync |
| Session playbook (Cursor + agents) | [`guides/cursor-session-playbook.md`](guides/cursor-session-playbook.md) | Ready (v1) | Sanitized; no secrets |
| Finding `BACKLOG.md` / paths | [`guides/finding-backlog-and-paths.md`](guides/finding-backlog-and-paths.md) | Ready | Workspace root, Cursor, terminal |
| AI context hygiene | [`guides/working-with-ai-context.md`](guides/working-with-ai-context.md) | Ready | Long threads, compaction; [`AGENTIC_CONTEXT_URLS.md`](../cursor-knowledge/AGENTIC_CONTEXT_URLS.md) (26 links) |
| Mobile web UX (tables, touch, responsive) | [`../cursor-knowledge/MOBILE_WEB_DESIGN_PRACTICES.md`](../cursor-knowledge/MOBILE_WEB_DESIGN_PRACTICES.md) | Ready (v1) | Data-heavy pages; **BL-17** / financial-reports; re-crawl sources yearly |
| Transcript scan (BL-10) | [`guides/enable-transcript-backlog-scan.md`](guides/enable-transcript-backlog-scan.md) | Ready v0 | [`scripts/scan_cursor_transcripts_for_backlog.py`](../../scripts/scan_cursor_transcripts_for_backlog.py) |
| Idea inbox + `/capture-idea` (BL-28) | [`../BACKLOG_INBOX.md`](../../BACKLOG_INBOX.md) | Ready v0 | Command [`.cursor/commands/capture-idea.md`](../../.cursor/commands/capture-idea.md); skill `backlog-inbox-capture` |
| Guides hub | [`guides/README.md`](guides/README.md) | Active | Playbook + path finder + room for more |
| Checklists | [`checklists/README.md`](checklists/README.md) | Stub | First-week, pre-share QA |
| Snippets | [`snippets/README.md`](snippets/README.md) | Partial | `a2b` backlog row + [`snippets/backlog-shortcut.md`](snippets/backlog-shortcut.md) |
| Git & GitHub for beginners | [`guides/git-basics-for-non-developers.md`](guides/git-basics-for-non-developers.md) | Ready (v1) | Clone, commit, push, GitHub Pages deploy; drawn from real deployment session |
| Curated links | [`links/README.md`](links/README.md) | Stub | Official Cursor + security |
| PM terms & acronyms (non-developer) | [`../product-management/GLOSSARY.md`](../product-management/GLOSSARY.md) | Ready (v0) | Plain definitions; journal **Glossary candidates** feed promotions |

**Publication:** When an item is ready for a public fork, mark **Published** and note target (e.g. `cursor-knowledge` repo). **Policy:** [Public vs private Git strategy](guides/public-vs-private-git-strategy.md) — triggers cheatsheet **public-friendly**; canonical **backlog** stays **private**.
