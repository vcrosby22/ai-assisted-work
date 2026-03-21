# Product backlog — best practices

**Who this is for:** Product builders, PMs, and anyone managing a list of "things we should build" — regardless of tool (Jira, Sheets, markdown, sticky notes). Non-technical readers welcome; no code required.

**What you will learn:** How to keep a backlog useful instead of letting it become a graveyard of stale ideas. Each section is self-contained — read what you need, skip what you don't.

**What this file is not:** Your actual prioritized backlog or personal change requests. Those belong in a **private** repository or tool. See [§7 in PM_KNOWLEDGE.md](PM_KNOWLEDGE.md) for how this repo separates public best practices from private work.

---

## Contents

- [1. What a product backlog actually is](#1-what-a-product-backlog-actually-is)
- [2. Refinement, ordering, and team habits](#2-refinement-ordering-and-team-habits)
- [3. Prioritization — choosing what comes next](#3-prioritization--choosing-what-comes-next)
- [4. Discovery vs delivery — are we building the right thing?](#4-discovery-vs-delivery--are-we-building-the-right-thing)
- [5. User stories — quality and splitting](#5-user-stories--quality-and-splitting)
- [6. Applying the ideas — what to do Monday morning](#6-applying-the-ideas--what-to-do-monday-morning)
- [Further reading](#further-reading)

---

## 1. What a product backlog actually is

A product backlog is an **ordered list** of everything a product might need — features, fixes, research, experiments, improvements. It is not a wish list, a parking lot, or a set of requirements frozen at the start of a project. Three things make it work:

**It is ordered, not just "prioritized."** Ordering means the team always knows what to work on next. A backlog where half the items are labeled "P1" has no real order — it just has a lot of items someone once called important.

**It serves a single Product Goal.** The Product Goal is the measurable long-term objective the backlog exists to achieve. Every item should contribute toward it. When new evidence arrives, you may reshape or abandon the goal — that is healthy, not failure. There is only one Product Goal at a time; a backlog serving five goals at once serves none.

**It is emergent.** The backlog changes as the team learns. Items are added, removed, split, and reordered continuously. A backlog that hasn't changed in a month is either perfect (unlikely) or neglected.

**One person decides.** The Product Owner (or whoever holds that accountability) is responsible for the backlog's content and ordering. Others contribute ideas and context, but one person makes the call so the team has a clear signal.

> **Source:** [The Scrum Guide (2020)](https://scrumguides.org/scrum-guide.html) — the authoritative definition of Product Backlog, Product Goal, and emergence. [Scrum.org — Product Goal](https://www.scrum.org/resources/product-goal).

---

## 2. Refinement, ordering, and team habits

Backlogs rot if you only look at them during planning. **Refinement** is the ongoing work of keeping the backlog useful — clarifying items, splitting large ones, re-estimating, and reordering as you learn.

### The DEEP framework

DEEP (Pichler / Cohn) describes what a healthy backlog looks like:

| Letter | Means | In practice |
|--------|-------|-------------|
| **D** | Detailed appropriately | Near-term items have acceptance criteria and clear scope. Far-future items are coarse headlines — one sentence is fine. |
| **E** | Estimated | Every item has a rough size (story points, t-shirt sizes, or hours). Precision increases as items move toward the top. |
| **E** | Emergent | Items are added, removed, split, and reordered as you learn. The backlog is never "done." |
| **P** | Prioritized | The top items are always the most valuable next work. The bottom is a loose pool, not a commitment. |

### Refinement is a habit, not a meeting

- **Rhythm:** Spend roughly 10% of your working time on refinement — clarifying upcoming items, splitting stories, updating estimates. If planning sessions are painful, your refinement habit is broken.
- **Collaboration:** The person who decides priorities and the people who do the work refine together. Writing items in isolation and handing them over creates surprises.
- **Ordering discipline:** If more than ~20% of your backlog is marked "highest priority," the word has lost meaning. Real ordering forces trade-offs — item 3 cannot also be item 1.

> **Further reading:** [Mountain Goat Software — Make the Product Backlog DEEP](https://mountaingoatsoftware.com/blog/make-the-product-backlog-deep) · [Scrum.org — Product backlog refinement](https://www.scrum.org/resources/product-backlog-refinement) · [Scrum.org — 5 reasons refinement is worth the time](https://www.scrum.org/resources/blog/5-reasons-why-refining-your-product-backlog-worth-time) · [Atlassian — Backlog refinement](https://www.atlassian.com/agile/scrum/backlog-refinement) · [Roman Pichler — Tips on refining the product backlog](https://www.romanpichler.com/blog/grooming-the-product-backlog/)

---

## 3. Prioritization — choosing what comes next

There is no single "correct" prioritization framework. The right one depends on your decision type, available data, and team size. Here is when to reach for each:

| Framework | Best for | How it works | Watch out for |
|-----------|----------|--------------|---------------|
| **RICE** | Large backlogs (30+ items) with usage data | **R**each × **I**mpact × **C**onfidence ÷ **E**ffort. Produces a numeric score. | False precision — a confidence of 50% vs 60% is a guess, not a measurement. |
| **ICE** | Weekly sprint-level decisions; teams without reach data | **I**mpact + **C**onfidence + **E**ase. Faster than RICE, drops Reach. | Easy to game by inflating "ease." |
| **MoSCoW** | Release scoping with stakeholders | **M**ust / **S**hould / **C**ould / **W**on't. Categorization, not ranking. | Everything becomes a "Must" unless you enforce limits. |
| **Kano** | Discovery — understanding what customers actually want | Survey-based: identifies **must-haves** (expected), **performance** (more is better), and **delighters** (unexpected joy). | Needs real customer data (50+ responses to be useful). |
| **WSJF** | Economic trade-offs — what delivers the most value soonest | Cost of Delay ÷ Job Size. Cost of Delay = user-business value + time criticality + risk reduction. | Requires honest sizing; teams often under-estimate job size. |
| **Pichler's four lenses** | Quick gut-check on any item | For each item ask: How **valuable**? How **risky** to delay? How **standalone** (releasable)? What does it **unblock** (dependencies)? | Informal — good for discussion, not for ranking 100 items. |

**Choosing:** Use **Pichler's lenses** or **ICE** for fast weekly decisions. Use **RICE** or **WSJF** when you need to justify a ranking to stakeholders or across a large backlog. Use **Kano** when you are still figuring out what customers care about. Use **MoSCoW** when scoping a specific release with business partners.

> **Further reading:** [Roman Pichler — Prioritising the Product Backlog](https://www.romanpichler.com/blog/prioritising-the-product-backlog/) · [Roman Pichler — Product backlog FAQs](https://www.romanpichler.com/blog/product-backlog-faqs/) · [Roman Pichler — 5 tips for stocking the product backlog](https://www.romanpichler.com/blog/5-tips-for-stocking-the-product-backlog/) · [SAFe — WSJF extended guidance](https://scaledagileframework.com/wsjf)

---

## 4. Discovery vs delivery — are we building the right thing?

The most common backlog failure is not bad ordering — it is building well-ordered items that **nobody needed**. Discovery is the work of figuring out *what* to build; delivery is building it. Most backlogs conflate the two.

### The Opportunity Solution Tree (Teresa Torres)

The OST is a visual hierarchy that prevents jumping from "idea" to "build" without validating a real problem:

```
Outcome (measurable business goal)
  └── Opportunity (customer need or pain point)
        └── Solution (possible way to address)
              └── Assumption test (cheap experiment before committing)
```

**Why it matters:** It forces you to name the **customer opportunity** before proposing a solution. "Build a dashboard" is a solution. "Users can't tell if their report is stale" is the opportunity. You might solve it with a dashboard, a timestamp, or an email — the tree makes you compare options instead of committing to the first idea.

### Two backlogs, not one

SVPG (Marty Cagan) draws a sharp line:

| Backlog type | Contains | When items enter |
|--------------|----------|------------------|
| **Opportunity backlog** | Validated problems and customer needs | After discovery conversations and evidence gathering |
| **Delivery backlog** | Committed solutions with clear acceptance criteria | After a solution has been validated against an opportunity |

If your single backlog mixes "we should explore whether users need X" with "build feature Y by Friday," you are conflating discovery and delivery. Separate them — even if the separation is just a column or label.

### The continuous discovery habit

At minimum: **one real customer or user touchpoint per week**, used to **discover opportunities** — not to confirm solutions already decided. This is the single habit that most consistently separates teams that build things people use from teams that build things nobody asked for.

> **Further reading:** [Teresa Torres — Opportunity Solution Trees](https://www.producttalk.org/2016/08/opportunity-solution-tree/) · [SVPG — The Opportunity Backlog](https://www.svpg.com/the-opportunity-backlog/) · [SVPG — Timeboxing Product Discovery](https://www.svpg.com/time-boxing-product-discovery/)

---

## 5. User stories — quality and splitting

A user story is a short statement of intent from a user's perspective. It is **not** a specification — it is a **placeholder for a conversation**. The card captures the essence; the details emerge through collaboration.

### The INVEST checklist

INVEST (Bill Wake) defines what makes a story ready to work on. Each criterion has a common failure mode:

| Criterion | What it means | Failure looks like |
|-----------|---------------|-------------------|
| **I**ndependent | Can be built and delivered without waiting for another story | Two stories that can only ship together |
| **N**egotiable | Details are co-created, not locked in the card | Treating the story as a legal contract; no room to adjust |
| **V**aluable | Delivers something a user or customer cares about | "Set up the database" — no user value on its own |
| **E**stimable | The team understands it well enough to size it | "Integrate with partner API" when nobody has read the API docs |
| **S**mall | Can be completed in days, not weeks | Stories that consume an entire sprint with no intermediate check |
| **T**estable | You can describe how to verify it works | "Make the UX better" — no observable success condition |

### The vertical slicing rule

**Always cut through all layers** (UI, logic, data) so each slice delivers something a user can see or use. Never split horizontally by layer ("build the database first, then the API, then the UI") — that delays feedback until everything is assembled.

### Nine splitting patterns (Richard Lawrence)

When a story is too large, use one of these patterns to break it down:

| Pattern | How to split | Example |
|---------|-------------|---------|
| **Workflow steps** | Build the simple end-to-end path first, add middle steps later | Checkout: start with "buy one item, default shipping"; add gift wrap and multi-address later |
| **Business rule variations** | Separate by different conditions or policies | Pricing: standard price first; loyalty discounts and bulk pricing as separate stories |
| **Data variations** | Split by categories or types of input | Reports: support CSV first, then PDF, then Excel |
| **CRUD operations** | Separate create, read, update, delete | User profile: "view profile" first, then "edit profile" |
| **Data entry methods** | Split by channel or actor | Order entry: web form first, then mobile app, then API |
| **Major effort** | Isolate the hard part | Payment: credit card first (known), then cryptocurrency (unknown) |
| **Simple / complex** | Do the 80% case, defer edge cases | Search: exact match first, then fuzzy matching and typo correction |
| **Defer performance** | Make it work, then make it fast | Report generation: correct results first; optimize query speed later |
| **Spike vs implementation** | Research first, build second | "Evaluate three mapping libraries" (spike), then "integrate chosen library" (build) |

**Decision rules:** Choose splits that let you **deprioritize or eliminate** low-value functionality. Choose splits that create **roughly equal-sized** stories so the Product Owner has maximum flexibility.

> **Further reading:** [Humanizing Work — Patterns for Splitting User Stories](https://agileall.wpengine.com/patterns-for-splitting-user-stories/) · [Mountain Goat Software — User stories](https://www.mountaingoatsoftware.com/agile/user-stories) · [XP123 — INVEST in Good Stories (Bill Wake)](https://www.xp123.com/articles/invest-in-good-stories-and-smart-tasks/)

---

## 6. Applying the ideas — what to do Monday morning

You do not need to adopt every framework above. Here is the minimum that makes a real difference:

1. **Start with a single ordered list.** Markdown table, Jira board, Notion page, sticky notes — the tool does not matter. What matters is that the list has an **order**, not just labels.

2. **Apply DEEP to the top.** Detail the top 5–10 items with clear scope and acceptance criteria. Leave the rest as coarse headlines. If you cannot describe what "done" looks like for a top item, it is not ready — refine it or move it down.

3. **Before adding anything new, ask:** "What customer opportunity does this serve?" If you cannot name the opportunity, the item is a solution looking for a problem. Park it; do discovery first.

4. **Refine weekly.** Spend 30–60 minutes reviewing the top of the backlog: split large items, reorder based on new information, remove anything that no longer matters. Monthly refinement is too slow; daily is too noisy.

5. **Split anything larger than one week of focused work.** Use the nine patterns above. If a story will take three weeks, it hides at least two decisions you haven't made yet.

6. **Use INVEST as a pre-flight checklist.** Before marking an item "ready to build," run through the six criteria. If it fails one, fix it before starting work — not during.

7. **Separate discovery from delivery.** Even a simple label ("exploring" vs "ready to build") prevents the team from committing to solutions they have not validated.

---

## Further reading

All links below are to external third-party sources. Bookmark what you trust.

| # | Resource | Topic |
|---|----------|-------|
| 1 | [The Scrum Guide](https://scrumguides.org/scrum-guide.html) | Backlog definition, Product Goal, emergence |
| 2 | [Scrum.org — What is a Product Backlog?](https://www.scrum.org/resources/what-is-a-product-backlog) | PO accountability, ordering |
| 3 | [Scrum.org — Product backlog refinement](https://www.scrum.org/resources/product-backlog-refinement) | What refinement is (and is not) |
| 4 | [Scrum.org — 5 reasons refinement is worth the time](https://www.scrum.org/resources/blog/5-reasons-why-refining-your-product-backlog-worth-time) | Case for ongoing refinement |
| 5 | [Atlassian — Backlog refinement](https://www.atlassian.com/agile/scrum/backlog-refinement) | Accessible primer |
| 6 | [Roman Pichler — Prioritising the Product Backlog](https://www.romanpichler.com/blog/prioritising-the-product-backlog/) | Value, risk, releasability, dependencies |
| 7 | [Roman Pichler — Product backlog FAQs](https://www.romanpichler.com/blog/product-backlog-faqs/) | Goal-oriented, emergent, ordered |
| 8 | [Roman Pichler — 5 tips for stocking the product backlog](https://www.romanpichler.com/blog/5-tips-for-stocking-the-product-backlog/) | Avoid garbage-in |
| 9 | [SVPG — The Opportunity Backlog](https://www.svpg.com/the-opportunity-backlog/) | Discovery vs delivery |
| 10 | [SVPG — Timeboxing Product Discovery](https://www.svpg.com/time-boxing-product-discovery/) | Cheap learning cycles |
| 11 | [Teresa Torres — Opportunity Solution Trees](https://www.producttalk.org/2016/08/opportunity-solution-tree/) | OST framework |
| 12 | [Mountain Goat Software — User stories](https://www.mountaingoatsoftware.com/agile/user-stories) | Story basics (Cohn) |
| 13 | [XP123 — INVEST in Good Stories (Bill Wake)](https://www.xp123.com/articles/invest-in-good-stories-and-smart-tasks/) | Story quality mnemonic |
| 14 | [Humanizing Work — Patterns for Splitting User Stories](https://agileall.wpengine.com/patterns-for-splitting-user-stories/) | Nine splitting patterns (Lawrence) |
| 15 | [SAFe — WSJF extended guidance](https://scaledagileframework.com/wsjf) | Cost of Delay / Job Size |
| 16 | [Mountain Goat Software — Make the Product Backlog DEEP](https://mountaingoatsoftware.com/blog/make-the-product-backlog-deep) | DEEP framework |
| 17 | [Roman Pichler — Tips on refining the product backlog](https://www.romanpichler.com/blog/grooming-the-product-backlog/) | Refinement practice |

---

*Last updated: 2026-03-21. Curated by [Victoria Crosby](https://github.com/vcrosby22). Extend with your org's standards (e.g. internal security review gates, compliance checklists).*
