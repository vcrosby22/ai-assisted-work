# Git & GitHub — A Beginner's Guide

## At a glance

=== "Beginner"

    Git is a tool that **saves versions** of your files — like "undo" on steroids. GitHub is a website where those versions live online so you can share them or publish a website. This guide teaches you the 5 commands you actually need: `clone`, `add`, `commit`, `push`, and `status`.

=== "Intermediate"

    Git version control fundamentals: clone a repo, stage changes (`git add`), commit with messages, push to remote, resolve basic conflicts. GitHub Pages for free static site hosting. Branch basics for separating experiments from main. GitHub CLI (`gh`) for authentication and pull requests from the terminal.

=== "Advanced"

    This guide is intentionally scoped to the non-developer workflow (linear history, single branch, terminal CLI). For branching strategies, CI/CD, submodule management, and the public/private repo split pattern used in this knowledge base, see [public vs. private Git strategy](public-vs-private-git-strategy.md) and the [session log](../../session-log.md) for real-world deployment examples.

---

**Audience:** Anyone who has never used Git before but needs to get code changes onto a live website (like GitHub Pages). Written from real experience deploying a financial report site.

**What you'll learn:** What Git is, what GitHub is, how to clone/copy/commit/push, and how to trigger a deploy — all from your terminal.

---

## What is Git?

Git is a tool that **tracks changes to files** over time. Think of it like "Track Changes" in Google Docs, but for code and entire folders.

- Every time you **commit**, Git saves a snapshot of your files at that moment
- You can go back to any previous snapshot if something breaks
- Multiple people can work on the same files without overwriting each other

Git lives **on your computer**. It works offline. You don't need the internet to save snapshots.

## What is GitHub?

GitHub is a **website that stores your Git snapshots online** (in a "repository" or "repo"). Think of it as cloud backup + collaboration for your code.

GitHub also offers extras:
- **GitHub Pages** — turns a repo into a live website (free)
- **GitHub Actions** — runs tasks automatically (like rebuilding a website on a schedule)
- **Pull Requests** — a way to propose and review changes before merging them

**Key distinction:** Git = the tool on your laptop. GitHub = the online service that hosts your repos.

---

## Essential vocabulary

| Term | Plain English |
|------|--------------|
| **Repository (repo)** | A project folder tracked by Git |
| **Clone** | Download a copy of a repo from GitHub to your computer |
| **Commit** | Save a snapshot of your current changes (with a short description) |
| **Push** | Upload your commits from your computer to GitHub |
| **Pull** | Download the latest changes from GitHub to your computer |
| **Branch** | A parallel version of your code (like a draft); `main` is usually the primary one |
| **Remote** | The GitHub copy of your repo (usually called `origin`) |
| **SHA / hash** | A unique ID for each commit (looks like `34bf56f`) |

---

## Setup (one time)

### 1. Install Git

**Mac:** Open Terminal and type `git --version`. If it's not installed, macOS will prompt you to install it (or install via [Homebrew](https://brew.sh): `brew install git`).

**Windows:** Download from [git-scm.com](https://git-scm.com/downloads).

### 2. Install GitHub CLI (optional but helpful)

```bash
brew install gh        # Mac
```

Then authenticate:

```bash
gh auth login
```

Follow the prompts — this saves your credentials so you don't have to type passwords.

### 3. Verify everything works

```bash
git --version
gh --version     # if you installed it
```

---

## The basics — your first workflow

### Clone a repo (download it)

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPO.git
cd YOUR-REPO
```

**Common mistake:** Getting "Repository not found" usually means:
- The URL has a typo (check exact username and repo name)
- The repo is **private** and you're not logged in — use `gh auth login` first
- Wrong username (e.g. `victoriacrosby22` vs `vcrosby22`)

**Tip:** Go to the repo on GitHub, click the green **Code** button, and copy the exact URL it shows.

### Make changes

Edit files however you normally would — in Cursor, VS Code, Finder, or any editor.

### See what changed

```bash
git status
```

This shows which files are new, modified, or deleted. **Red** = not yet staged. **Green** = staged and ready to commit.

### Stage and commit (save a snapshot)

```bash
git add .                     # stage all changed files
git commit -m "Short description of what you changed"
```

Or stage specific files:

```bash
git add src/report.py src/analysis/risk.py
git commit -m "Update report layout and fix risk scoring"
```

**Tip:** Commit messages should say **what** and **why**, not how. Good: "Fix missing score field for CI deploy." Bad: "Updated file."

### Push (upload to GitHub)

```bash
git push origin main
```

This sends your commits to GitHub. After this, anyone (or any automation) looking at the repo online will see your changes.

### Pull (download latest from GitHub)

```bash
git pull origin main
```

Always pull before you start working if someone else (or a scheduled action) might have changed files.

---

## Deploying to a live website (GitHub Pages)

This is where Git meets "my website." GitHub Pages turns a repo into a website at `https://USERNAME.github.io/REPO-NAME/`.

### How it typically works

1. You **push** code to `main`
2. A **GitHub Action** (automated script) runs: builds your site, generates HTML
3. The Action publishes the HTML to a `gh-pages` branch or `docs/` folder
4. GitHub Pages serves that HTML as your website

### When your site doesn't update after pushing

**This is the most common confusion for beginners.** Pushing code to `main` does NOT always update the site. Here's why:

- The **Action** (workflow) might only run on a **schedule** (e.g. twice daily), not on every push
- If the Action **fails**, the old site stays up — nothing breaks, but nothing updates either

### How to check and fix

1. Go to your repo on GitHub → **Actions** tab
2. Look at the latest run:
   - **Green checkmark** = succeeded; site should update within a few minutes
   - **Red X** = failed; site stays at whatever was last successfully deployed
   - **No new run** after your push = the workflow doesn't trigger on push

### Manually trigger a deploy

If the workflow supports `workflow_dispatch`:

1. **Actions** → click the workflow name (e.g. "Daily Market Report")
2. Click **Run workflow** → select branch **`main`** → **Run workflow**
3. Wait for it to finish green

### Make deploys automatic on push

Add this to your workflow YAML file (`.github/workflows/your-workflow.yml`) under the `on:` section:

```yaml
on:
  push:
    branches: [main]
  schedule:
    - cron: '0 12 * * 1-5'
  workflow_dispatch:
```

Now pushes to `main` will also trigger the build.

---

## When things go wrong

### "Repository not found"

- Check the **exact** URL (username, repo name, capitalization)
- Make sure you're authenticated: `gh auth status`
- If the repo is private, you need access

### Action fails with a Python error

Read the error log:
1. **Actions** → click the failed run → click the failed **job** → expand the failed **step**
2. Look for a **Traceback** — the last line tells you the actual error
3. Common causes:
   - **`ImportError`** / **`ModuleNotFoundError`** — a file is missing or out of date
   - **`AttributeError`** — code expects something that doesn't exist in an older file version
   - **Fix:** sync ALL related files, not just the one you edited

### "Everything is up to date" but site looks old

- The Action might not have run yet — check **Actions** tab
- Browser cache — try **incognito/private** window or hard refresh (Cmd+Shift+R on Mac)
- GitHub Pages CDN can take 2–10 minutes to update after a successful deploy

### Accidentally committed something wrong

Don't panic. Before pushing:

```bash
git reset HEAD~1     # undo the last commit, keep your file changes
```

If you already pushed, talk to someone before force-pushing — it rewrites history and can affect others.

---

## Syncing two repos (private workspace → public deploy)

Sometimes you develop in a **private** repo and deploy from a **public** one (this is common for keeping journals/secrets separate from what's published).

### The pattern

```
Private repo (where you work)     Public repo (what's deployed)
financial-agent/src/report.py  →  financial-reports/src/report.py
```

### How to sync

```bash
# 1. Go to your public repo clone
cd /path/to/financial-reports

# 2. Pull latest
git pull origin main

# 3. Copy files from private repo
cp /path/to/financial-agent/src/report.py ./src/report.py
# ... copy all files that changed

# 4. Commit and push
git add -A
git commit -m "Sync from private repo: describe what changed"
git push origin main

# 5. Trigger deploy if needed (Actions → Run workflow)
```

**Critical lesson:** Copy **all** files that import each other, not just the one you edited. If `report.py` imports from `risk.py`, and `risk.py` is outdated on the public repo, the build will fail with an `ImportError` or `AttributeError`.

---

## Quick reference card

| What you want to do | Command |
|---------------------|---------|
| Download a repo | `git clone URL` |
| See what changed | `git status` |
| Save changes locally | `git add . && git commit -m "message"` |
| Upload to GitHub | `git push origin main` |
| Download latest | `git pull origin main` |
| Check GitHub login | `gh auth status` |
| View recent commits | `git log --oneline -5` |
| Undo last commit (before push) | `git reset HEAD~1` |

---

## Learning more

- [GitHub's official "Git Handbook"](https://docs.github.com/en/get-started/using-git/about-git) — short, visual
- [Git — the simple guide](https://rogerdudler.github.io/git-guide/) — one-page cheat sheet
- [GitHub Skills](https://skills.github.com/) — free interactive courses
- [Oh My Git!](https://ohmygit.org/) — learn Git through a game
- [Dangit, Git!?!](https://dangitgit.com/) — how to fix common mistakes in plain English
- [GitHub Pages docs](https://docs.github.com/en/pages) — setting up and configuring your site
- [GitHub Actions quickstart](https://docs.github.com/en/actions/quickstart) — understand workflows and triggers

---

*Written from real deployment experience: cloning, syncing files between repos, debugging CI failures, and getting a financial report live on GitHub Pages. Every "gotcha" in this guide happened in practice.*
