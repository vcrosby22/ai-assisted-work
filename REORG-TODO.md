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
- [x] Decide what belongs in personal `vcrosby22/ai-assisted-work` vs. `ProgramEdgeLLC/*`. *(2026-06-23: this public repo now holds only shareable KB + `projects/college-advising/` (intended public mirror). SSFA, equine, and peptide all removed and gitignored.)*
- [x] Relocate `equine-therapy-nonprofit/` planning docs to a private home. *(2026-06-23: reconciled against the private `ProgramEdgeLLC/center-x-equine-therapy-site` repo — all but `poc-homepage.html` were identical/older subsets of docs already there; `poc-homepage.html` archived to that repo's non-deployed `_parked/`. Public copy deleted + gitignored. Verified the Center X Pages deploy serves `public/` only, so root planning docs are NOT published.)*
- [x] Remove personal `peptide-knowledge-base` from this PUBLIC repo. *(2026-06-23: never published (404); 2 unique files preserved into the private parent `peptide-knowledge-base/` on disk; public copy deleted + gitignored.)*
- [ ] Finish Cloudflare account split (business/client vs. personal).
- [x] Harden the `center-x-equine-therapy-site` repo. *(2026-06-23: moved all internal/sensitive root files — handoffs, client notes, plans, HIPAA-vendor CSV, client bio PDF, `setup/` runbooks — into `_private/`; only `public/` + `README.md` remain at root. Added `.assetsignore` safety net + rewrote the stale README with the deploy contract. **Still verify in the CF dashboard:** Pages build output dir = `public/`.)*

## Resolved 2026-06-23 (privacy incident + cleanup)
This PUBLIC repo had client work committed into it (`projects/susan-street-gallery/` incl. a CMS migration plan, and `projects/equine-therapy-nonprofit/`). Fixed: untracked + gitignored both, **scrubbed all git history** (filter-branch on a fresh clone, force-push), verified 404 on GitHub, fixed the orphaned `cursor-knowledge-public` submodule pin in the private parent, and homed the SSFA docs privately in `ProgramEdgeLLC/ssfa-redesign-poc/planning/`. Pre-scrub backup bundle: `~/Desktop/ai-assisted-work-PRESCRUB-backup-2026-06-23.bundle`.
