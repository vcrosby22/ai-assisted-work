# Folder / Repo / Git Cleanup & Re-org — TODO

> Parked note (created 2026-06-22). Do a deliberate cleanup of local folders,
> git repos, and client-vs-personal separation when there's time.

## Why this is needed (observed state)

1. **Duplicate `ai-assisted-work` folders on Desktop:**
   - `~/Desktop/Cursor/ai-assisted-work` — near-empty shell, **not a git repo**, only
     contains a stray `projects/program-edge/` folder. (This was the folder Cursor
     had open by default.)
   - `~/Desktop/AI Builder Projects/ai-assisted-work` — the **real** clone: git repo,
     remote `github.com/vcrosby22/ai-assisted-work` (personal), holds `design-knowledge/`
     KB + all `projects/` incl. `susan-street-gallery/`. **This is the canonical one.**
   - ➜ Decide on ONE canonical location; delete/merge the empty Cursor/ copy.

2. **Personal vs. Program Edge (client) separation is inconsistent:**
   - Client work *should* live in the `ProgramEdgeLLC` GitHub org (pattern already
     used: `ProgramEdgeLLC/program-edge-site`, `ProgramEdgeLLC/center-x-equine-therapy-site`).
   - But the **Susan Street Fine Art** work currently sits inside the **personal**
     `vcrosby22/ai-assisted-work` repo under `projects/susan-street-gallery/`.
   - The SSFA **POC code (`poc/`) is not committed anywhere** — only the 2 markdown
     deliverables are tracked. Live site `ssfa-redesign-poc.pages.dev` was a direct
     `wrangler` upload (no connected git repo).
   - ➜ Decide: create `ProgramEdgeLLC/ssfa-redesign-poc` (or similar), move `poc/`
     there, connect Cloudflare Pages to the repo (vs. continuing direct uploads).

3. **Cloudflare account:** business + client projects (`program-edge.com`,
   `center-x-equine-therapy`, `ssfa-redesign-poc`) live in one account being renamed
   to "Program Edge LLC"; truly personal projects (blog, financial-reports, toolwitness)
   to be moved to a separate "Personal" account later.

## Suggested cleanup checklist (refine before doing)
- [x] Pick canonical local root for `ai-assisted-work`; remove the duplicate empty copy. *(2026-06-23: canonical = `~/Desktop/AI Builder Projects/ai-assisted-work`; deleted the stray `~/Desktop/Cursor/ai-assisted-work` shell.)*
- [x] Reconcile the stray `~/Desktop/Cursor/ai-assisted-work/projects/program-edge`. *(2026-06-23: its one file `design-audit-2026-06-18.md` was a confirmed duplicate of `Program Edge/_private/docs/`; shell deleted.)*
- [x] Move SSFA work into its own repo. *(2026-06-23: `ProgramEdgeLLC/ssfa-redesign-poc` (private) restructured to `site/` (deployed) + `planning/` (internal docs); planning docs moved out of this PUBLIC repo and history-scrubbed.)*
- [~] Decide what belongs in personal `vcrosby22/ai-assisted-work` vs. `ProgramEdgeLLC/*`. *(2026-06-23: SSFA + equine client folders removed from this public repo; `college-advising` kept as intended public mirror. **Still open:** `projects/equine-therapy-nonprofit/` planning docs remain on disk (untracked, unpublished) and want a private home — see below.)*
- [ ] Create per-client org repos for remaining client work (e.g. relocate `equine-therapy-nonprofit/` planning docs to a private Program Edge home; do NOT put them in the deploy root of `center-x-equine-therapy-site`).
- [ ] Finish Cloudflare account split (business/client vs. personal).

## Resolved 2026-06-23 (privacy incident + cleanup)
This PUBLIC repo had client work committed into it (`projects/susan-street-gallery/` incl. a CMS migration plan, and `projects/equine-therapy-nonprofit/`). Fixed: untracked + gitignored both, **scrubbed all git history** (filter-branch on a fresh clone, force-push), verified 404 on GitHub, fixed the orphaned `cursor-knowledge-public` submodule pin in the private parent, and homed the SSFA docs privately in `ProgramEdgeLLC/ssfa-redesign-poc/planning/`. Pre-scrub backup bundle: `~/Desktop/ai-assisted-work-PRESCRUB-backup-2026-06-23.bundle`.
