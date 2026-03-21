# Public document quality criteria

**Who this is for:** Anyone creating or reviewing files in the public [`cursor-knowledge`](https://github.com/vcrosby22/cursor-knowledge) repository. These criteria treat every public markdown file as a **product** — with a user, a purpose, and a UI (the GitHub renderer).

**Why this exists:** A collection of markdown files is not automatically useful. Without intentional design, public docs become stale, hard to navigate, and full of broken links to private repos. These criteria define what "good" looks like.

---

## Contents

- [The core test](#the-core-test)
- [Nine quality criteria](#nine-quality-criteria)
- [Applying this to a file](#applying-this-to-a-file)
- [Anti-patterns](#anti-patterns)

---

## The core test

Before publishing or updating any file, ask:

> **Could a first-time visitor — someone who has never seen this repo — find, read, understand, and act on this document within 5 minutes?**

If the answer is no, the file needs work.

---

## Nine quality criteria

Each criterion includes a **one-line test** you can use as a checklist.

| # | Criterion | What it means | Test |
|---|-----------|---------------|------|
| 1 | **User** | The file has a defined audience. | Audience is stated in the first two lines. |
| 2 | **Purpose** | One file, one job. | You can describe the file's job in one sentence. |
| 3 | **Navigation** | Table of contents, anchor links, clear heading hierarchy. | A reader can find what they need from headings alone, without scrolling the full document. |
| 4 | **Scannable structure** | Tables for comparisons; bold key terms; short paragraphs. | A 60-second skim of headings and bold text delivers the core ideas. |
| 5 | **Actionable content** | Real synthesized knowledge, not just a list of links. | Someone could act on this without clicking a single external link. |
| 6 | **Self-contained on GitHub** | No broken links to private repos or monorepo-only paths. | Every link resolves on a fresh clone of `cursor-knowledge`. |
| 7 | **Entry points** | README and INDEX provide "start here" paths by reader type. | A first-time visitor finds the right file in under 30 seconds from the repo root. |
| 8 | **Freshness signal** | Date or version at the bottom. | A reader can tell how current the content is. |
| 9 | **Concise** | Every paragraph serves the stated audience. | Nothing is there "just in case" — more content makes information harder to find. |

---

## Applying this to a file

### Before writing

1. **Name the user.** Who will read this? What are they trying to accomplish?
2. **Name the job.** What will the reader be able to do after reading that they could not do before?
3. **Check the tree.** Does this file already exist under a different name? Could the content live in an existing file instead?

### While writing

4. **Lead with the point.** The first two sentences should tell the reader whether this file is for them.
5. **Use progressive disclosure.** Summary at the top, detail in the middle, citations and further reading at the bottom. A reader who leaves after 60 seconds should still get value.
6. **Use tables for structured information.** Comparisons, checklists, decision guides, and pattern catalogs render well on GitHub and are faster to scan than prose.
7. **Bold the terms that matter.** A reader scanning only bold text should get the skeleton of the argument.
8. **Add a table of contents** with anchor links for any file longer than three screen-heights.

### Before merging

9. **Link check.** Click every link. Does it resolve on a fresh clone? Links to `../../BACKLOG.md`, `../../.cursor/`, or `../../scripts/` will 404 for public readers.
10. **Freshness.** Add or update the "last updated" line at the bottom.
11. **Entry point check.** Is this file reachable from `README.md` or `INDEX.md`? If not, add it.

---

## Anti-patterns

| Pattern | Why it fails | Fix |
|---------|-------------|-----|
| **Link dump** | A table of URLs with one-line annotations provides no value over a Google search. | Synthesize the key ideas inline; keep links as "further reading." |
| **Wall of text** | Long unbroken prose is not scannable on a screen. | Break into sections with headings, tables, and bold key terms. |
| **Audience of everyone** | "This is for anyone interested in product management" means it is designed for no one. | Name a specific reader and their goal in line 1. |
| **Private path leakage** | Links to `../../BACKLOG.md` or `.cursor/` that only exist in the private monorepo. | Use `onboarding/INDEX-full-workspace-only.md` for those paths; keep the main file self-contained. |
| **Stale content** | No date, no version, no signal of currency. | Add "last updated" at the bottom; remove or flag content you cannot verify is current. |
| **One file, many jobs** | A file that is simultaneously a glossary, a tutorial, and a reading list. | Split into focused files; link between them. |

---

*Last updated: 2026-03-21. This document governs all public files in [`vcrosby22/cursor-knowledge`](https://github.com/vcrosby22/cursor-knowledge).*
