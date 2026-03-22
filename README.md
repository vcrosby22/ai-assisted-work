# Learn Cursor — a guide for non-technical people

**Cursor** is a code editor with a built-in AI assistant. You don't need to be a developer to use it. People use Cursor to write, plan, research, build simple websites, and turn ideas into working prototypes — by *talking* to the assistant instead of writing code from scratch.

This repository is a **free, open collection** of guides, checklists, and reference material to help you get started and get better over time.

---

## Start here

| Step | What you'll do | Link |
|------|---------------|------|
| **1** | Install Cursor and have your first conversation | [**Getting started**](onboarding/guides/installing-cursor-and-first-steps.md) |
| **2** | Understand the mindset: you steer, the AI builds | [**Building with agentic AI (non-technical)**](onboarding/guides/building-with-agentic-ai-non-technical.md) |
| **3** | Work through your first week at your own pace | [**First-week checklist**](onboarding/checklists/first-week-cursor-non-technical.md) |

After that, pick a **learning path** based on where you are:

| Path | You are… | Start with |
|------|----------|------------|
| **A — Brand new** | Never used AI tools; want quick wins without the terminal | Steps 1–3 above → [AI context guide](onboarding/guides/working-with-ai-context.md) → [Session playbook](onboarding/guides/cursor-session-playbook.md) |
| **B — Ready for Git** | Want to save versions or share work on GitHub | [Git basics for non-developers](onboarding/guides/git-basics-for-non-developers.md) → [Public vs private Git](onboarding/guides/public-vs-private-git-strategy.md) |
| **C — Power user** | Setting up rules, backlogs, and automation in a private workspace | [Full onboarding catalog](onboarding/INDEX.md) including [workspace-only extras](onboarding/INDEX-full-workspace-only.md) |

---

## Quick answers

**Do I need to know how to code?** No. Many people use Cursor for writing, planning, and "no-code" style work. The guides here assume zero programming experience.

**Is Cursor free?** Cursor has a free tier with limited AI usage. Paid plans unlock more. See [cursor.com/pricing](https://www.cursor.com/pricing).

**What can I actually build?** Landing pages, documents, research summaries, structured plans, simple web apps, data analysis scripts, and more — depending on how far you want to go. Start with ideas you already have.

**What if I break something?** Cursor has undo. Git (version control) lets you go back to any saved point. The guides here teach both.

---

## What's in this repo

| Folder | What's inside | Who it's for |
|--------|--------------|--------------|
| [`onboarding/`](onboarding/) | **Guides, checklists, and reference material** for learning Cursor and working with AI | Everyone — start here |
| [`product-management/`](product-management/) | PM frameworks, a [plain-language glossary](product-management/GLOSSARY.md), and backlog best practices | PMs, product people, and anyone who wants definitions |
| [`cursor-knowledge/`](cursor-knowledge/) | Deeper articles on AI context, mobile UX, Git onboarding, and backlog philosophy | Intermediate readers and reference |
| [`session-log.md`](session-log.md) | The maintainer's build diary — real sessions showing what was built and what was learned | Curious readers; this is an example, not a tutorial |

Other files at the root: [`PROJECT_CONTEXT.md`](PROJECT_CONTEXT.md) is a **template** you can copy into your own workspace. [`LICENSE`](LICENSE) is CC BY 4.0.

---

## Curated links

- [Cursor documentation](https://docs.cursor.com/) — official product docs
- [Cursor pricing](https://www.cursor.com/pricing) — free and paid plans
- [GitHub Docs — Get started](https://docs.github.com/en/get-started) — repos, commits, collaboration
- [More curated links](onboarding/links/README.md) — safety, privacy, research literacy

---

## About this project

This knowledge base is maintained by **Victoria Crosby** ([@vcrosby22](https://github.com/vcrosby22)), a Technical Project Manager who uses Cursor daily and shares what works.

It grew out of a private workspace where Victoria journals, builds projects, and captures lessons learned. The guides and frameworks here are the **shareable parts** — cleaned up for anyone to use.

**License:** [CC BY 4.0](LICENSE) — share and adapt with attribution.

### For contributors and maintainers

<details>
<summary>Technical details (click to expand)</summary>

- The private workspace [where_cursor_feels_home](https://github.com/vcrosby22/where_cursor_feels_home) vendors this repo as a **git submodule** at `cursor-knowledge-public/` with symlinks for `onboarding/` and `product-management/`.
- Links that point "up" to `BACKLOG.md`, `scripts/`, or `.cursor/` resolve only inside that private clone.
- Quality standard for all public files: [`product-management/PUBLIC_DOC_QUALITY_CRITERIA.md`](product-management/PUBLIC_DOC_QUALITY_CRITERIA.md).
- Before contributing: remove secrets, tokens, and personal data. See [`onboarding/guides/public-vs-private-git-strategy.md`](onboarding/guides/public-vs-private-git-strategy.md).

</details>
