# Git & GitHub Onboarding — Knowledge Base

**Category:** Developer onboarding · Non-technical users · Deployment workflow  
**Source session:** 2026-03-20 (BL-17 deployment to GitHub Pages)  
**Companion guide:** [`onboarding/guides/git-basics-for-non-developers.md`](../onboarding/guides/git-basics-for-non-developers.md)

---

## Context

During deployment of the financial market report to GitHub Pages, we encountered every common beginner Git & deployment pitfall: wrong clone URLs, silent workflow triggers, partial file syncs causing CI failures (`AttributeError`, `ImportError`), and cache confusion when the site "didn't update." This knowledge base captures the patterns so they don't have to be re-learned.

## Key patterns

### 1. Clone URL must be exact

- **Wrong username** or **wrong repo name** → "Repository not found"
- Always copy the URL from GitHub's green **Code** button
- Private repos need authentication (`gh auth login`)

### 2. Pushing to `main` does not always deploy

GitHub Actions workflows only run when their `on:` triggers match. Common setup:

```yaml
on:
  schedule:
    - cron: '0 12 * * 1-5'
  workflow_dispatch:
```

This runs on a schedule and on-demand — but NOT on push. Add `push: branches: [main]` if you want automatic deploys on every push.

### 3. Sync ALL dependent files, not just what you edited

If `report.py` imports from `risk.py` and `ai_analyst.py`, and you only copy `report.py` to your deploy repo, the build will fail when it tries to call functions that don't exist in the older copies of those files.

**Rule:** When syncing between repos, copy the entire `src/` directory (plus `requirements.txt` and `config.yaml`) every time. The few extra seconds of copying prevent hours of debugging `ImportError` / `AttributeError` failures.

### 4. "Site didn't update" troubleshooting checklist

| Check | How |
|-------|-----|
| Did the workflow run? | GitHub → Actions tab → look for a run matching your commit SHA |
| Did it succeed? | Green checkmark = yes; Red X = build broke, old site stays up |
| Browser cache? | Try incognito/private window or Cmd+Shift+R |
| CDN propagation? | Wait 2–10 minutes after a successful deploy |
| Wrong branch? | Confirm GitHub Pages source is `gh-pages` branch (Settings → Pages) |

### 5. Read CI logs from the bottom up

When a GitHub Action fails:
1. Actions → click the failed run → click the failed job → expand the failed step
2. Scroll to the **Traceback** — the last line is the actual error
3. The error almost always points at a specific file and line number

## Lessons learned (from this session)

| Lesson | Detail |
|--------|--------|
| URL precision matters | `victoriacrosby22` ≠ `vcrosby22` — one character difference causes "not found" |
| Partial syncs are fragile | Two consecutive CI failures were caused by syncing only 2 of 15+ Python files |
| Manual `workflow_dispatch` is the escape hatch | When auto-triggers don't exist, you can always manually run from the Actions tab |
| Commit messages should help future-you | "Sync all src files for Pages deploy" is searchable; "updated stuff" is not |
| `git status` before `git push` | Catches accidental inclusions (`.env`, data files) before they're public |

## Curated learning resources

| Resource | What it is | Best for |
|----------|-----------|----------|
| [GitHub Git Handbook](https://docs.github.com/en/get-started/using-git/about-git) | Official intro | First-time readers |
| [Git — the simple guide](https://rogerdudler.github.io/git-guide/) | One-page cheat sheet | Quick reference |
| [GitHub Skills](https://skills.github.com/) | Interactive courses | Hands-on learning |
| [Oh My Git!](https://ohmygit.org/) | Visual game | People who learn by doing |
| [Dangit, Git!?!](https://dangitgit.com/) | Fix common mistakes | When something goes wrong |
| [GitHub Pages docs](https://docs.github.com/en/pages) | Setup & config | Deploying a site |
| [GitHub Actions quickstart](https://docs.github.com/en/actions/quickstart) | Workflow basics | Understanding CI/CD |

## Artifact inventory

| Artifact | Path | Audience |
|----------|------|----------|
| Beginner guide | `onboarding/guides/git-basics-for-non-developers.md` | Non-technical; first-time Git users |
| Knowledge base (this file) | `cursor-knowledge/GIT_GITHUB_ONBOARDING.md` | Anyone maintaining the knowledge base |
| Porting guide | `financial-agent/PORTING.md` | Contributors syncing to financial-reports |

---

*Extracted from real deployment session. All gotchas in this document were encountered in practice.*
