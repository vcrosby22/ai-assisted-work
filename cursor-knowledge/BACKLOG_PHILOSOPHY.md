# Backlog philosophy (workspace + agent capability building)

**Purpose:** Single reference for what “backlog” means here, how we **capture** work from conversation, and how to structure a backlog if the goal is **compounding agent + human capability** over time.

**Canonical prioritized list:** [`BACKLOG.md`](../../BACKLOG.md) (repo root) — rules: `.cursor/rules/backlog-prioritization.mdc`, `.cursor/rules/backlog-notify.mdc`. **Epic → Story → Description:** [`BACKLOG_STORY_DETAILS.md`](../../BACKLOG_STORY_DETAILS.md), [`BACKLOG_HIERARCHY.md`](../../BACKLOG_HIERARCHY.md). **Product backlog URLs (13+):** [`BACKLOG_PRODUCT_PRACTICES_URLS.md`](BACKLOG_PRODUCT_PRACTICES_URLS.md).

**Rich tickets (optional):** Field definitions, epic keys (`EP-NN`), templates, and `TKT-NNNNN` keys live under [`backlog/`](../backlog/README.md) — see [`backlog/TICKETING_MODEL.md`](../backlog/TICKETING_MODEL.md). The root table stays the **slim ordered index**; full markdown tickets are for history, assignee, and paste-friendly descriptions.

**Related:** `PRIMARY_OBJECTIVES.md`, Jira/Sheets tooling TBD, `.cursor/skills/feed-primary-objective/SKILL.md`, [`onboarding/`](../onboarding/README.md).

---

## 1. Traditional definitions (external anchors)

### General project / agile usage

Per [awork — Backlog (glossary)](https://www.awork.com/glossary/backlog): a backlog is an **evolving list** of tasks, requirements, or features **not yet completed**, used to **plan**, **prioritize**, and **track progress** — with practices like **regular updates**, **clear prioritization**, **consistent item descriptions**, and **visibility** to the right people.

**Nuance:** In the broad sense, “backlog” is **tool-agnostic** (Jira, Sheets, markdown). It is **not** the same as a **committed** timeboxed plan — it is the **pool from which** commitments are pulled.

### Scrum (precise vocabulary)

The [Scrum Guide](https://scrumguides.org/) distinguishes:

| Artifact | Meaning |
|----------|--------|
| **Product backlog** | **Emergent, ordered list** of what is needed to **improve the product**; **single source of work** for the team on that product ([Scrum.org — Product Backlog](https://www.scrum.org/resources/what-is-a-product-backlog)). |
| **Sprint backlog** | **Subset** committed for **one Sprint**, plus a plan to deliver **Done** work. |

**Nuance:** “Product” can be a **service**, internal tool, or **capability substrate** — not only customer-facing software. For a solo operator, “Scrum team” collapses to **you + agents**, but the **ordering + emergence** ideas still reduce chaos.

---

## 2. Working definition (this workspace)

> **Backlog** = an **ordered, living inventory of candidate work** — ideas and commitments-in-waiting — used to **prioritize**, **plan**, and **track** what gets done next, with enough structure that **future-you** (and collaborators) can reason without re-deriving everything from chat memory.

**Not the same as:** unbounded idea dumps with no ordering, or a **roadmap** narrative with dates (unless we explicitly link items to horizons).

---

## 3. Capture use cases (why one process is not enough)

Victoria’s intent: many items arise in discussion; **scope**, **time**, **attention**, and **risk** differ. Treat these as **different intake lanes** so triggers and fields can differ.

| Lane | Typical trigger | What “good capture” includes | Process note |
|------|-----------------|------------------------------|--------------|
| **A. Deferred work** | “We’ll do that **later**,” **out of scope this sprint/session**, **post-MVP**, **parking lot** | Link to **source** (chat/session), **why deferred**, **rough epic**, **reactivate condition** (e.g. “after public report stable”) | *Automatic assist:* when user or assistant **explicitly defers**, draft a backlog row; user confirms or edits. |
| **B. Recommendations not taken** | User **ignores**, **declines**, or **forgets** an assistant suggestion; or says “**not now**” without a defer reason | **What was recommended**, **assumed benefit**, **cost/risk**, **why skipped** (unknown ok) | *Automatic assist:* assistant ends relevant turns with **optional** “**Backlog candidate**” one-liner; only **writes** to canonical backlog when user says **capture** / **yes** / **add to backlog** (avoids nagging). |
| **C. Horizon / invention** | Large **bets**, **new systems**, **architecture pivots**, “**huge** idea” | **Outcome**, **non-goals**, **dependencies**, **spike vs build**, **minimum slice** | Often stays **large** until **refinement** (Scrum: product backlog refinement); may spawn **child** items in lanes A/B. |

**Design principle:** **Automation suggests, human commits** for anything that changes external systems (Jira, Sheets) or sensitive scope — aligned with common **human-in-the-loop** patterns in agent improvement discourse (e.g. proposals reviewed before “deploying” behavior changes).

---

## 4. Research touchpoints (agent capability backlogs)

These are **adjacent** patterns, not prescriptions:

- **Feedback loops:** Systems that improve often separate **proposal** → **review** → **apply** (evaluation, production signals, human edit as “gold”) — see e.g. [AgentC2 — self-improving agent](https://agentc2.ai/blog/how-to-build-self-improving-ai-agent) (general architecture ideas).
- **Hierarchical goals:** Manager-style decomposition (**outcome** → **tasks** → **verify**) reduces coordination load — e.g. [Zylos — hierarchical agent coordination](https://zylos.ai/research/2026-03-01-hierarchical-ai-agent-coordination) (research framing).
- **Deferral / resume:** Checkpointing long workflows maps to “we paused; don’t lose the **why**” — e.g. [Zylos — checkpointing](https://zylos.ai/research/2026-03-04-ai-agent-workflow-checkpointing-and-resumability) (research framing).

Use these to **inform** backlog **states** and **quality gates**, not to over-engineer a personal repo.

---

## 5. If building the “perfect” backlog for **agent self-capability** (opinionated structure)

If the product is **“the collaboration substrate”** (skills, rules, knowledge, evals, tools), a useful structure is **five layers** — from stable intent down to executable work:

### Layer 0 — Capability themes (stable buckets)

Map to **epics** (e.g. AI skills, rules, foundational AI knowledge, traditional technical foundations, AI prime objectives — plus optional **Collaboration & Cursor workflow**, **Shipping & spin-outs**). Themes change **slowly**.

### Layer 1 — Outcomes / bets (6–18 month horizon)

Each item names **observable capability**: “We can reliably X without Y failure mode.” **Not** a pile of tasks yet.

### Layer 2 — Programs or initiatives (weeks–quarters)

Grouped work with a **definition of done** for the program (e.g. “website-qa skill + one live run,” “backlog Jira sync v0”).

### Layer 3 — Backlog items (ordered, emergent)

Concrete PBIs / issues: sized enough to **prioritize**. Scrum’s **ordering + refinement** applies ([Scrum.org — refinement](https://www.scrum.org/resources/what-is-a-product-backlog)).

### Layer 4 — Committed slice (timeboxed)

What “**this week / this session**” actually takes on — the **sprint backlog** analogue. **Small WIP** to protect focus.

**Cross-cutting tracks (not separate backlogs unless volume forces it):**

| Track | Holds |
|-------|--------|
| **Intake / triage** | Raw captures from lanes A–C before they become Layer 3 items |
| **Quality & eval** | “How we know capability improved” (checklists, regression prompts, `/website-qa`-style gates) |
| **Governance / safety** | Items affecting **rules**, **secrets**, **visibility** — higher scrutiny before merge |

**Anti-patterns to avoid:**

- One undifferentiated list → everything feels equally urgent.
- No **commitment** boundary → backlog anxiety (“infinite list”).
- Auto-writing Jira/Sheets on every stray sentence → noise and **trust** erosion.

---

## 5b. Workspace practice — `Backlog candidates` in daily journals

Each **`journal/.../daily.md`** includes **`Backlog candidates (from this session)`** (see `journal/daily-journal-template.md`). That section is **assistant-assisted** at **`/session-end`** or substantive wrap-ups, scoped to **the current chat** unless the user supplies more context.

Weekly reviews roll those lines up under **`Carry-over from journals`** (`journal/weekly-review-template.md`).

---

## 6. Automation boundaries (draft policy)

| Behavior | Policy |
|----------|--------|
| User says “**later** / **defer** / **parking lot**” | Assistant **proposes** a structured capture (lane A); user confirms once. |
| Assistant recommends change user doesn’t adopt | Assistant may offer **one-line backlog candidate** (lane B); **no** auto-write to canonical store without confirmation. |
| Big idea surfaces | Assistant **summarizes** bet + suggests **first thin slice** (lane C → Layer 3). |
| Session end | Optional: `activeContext.md` / journal “**Tasks for Later**” stays **short**; meatier items promoted to **canonical backlog** when tooling exists. |

Refine when Jira/Sheets integration exists.

---

## 7. Changelog

- **2026-03-23** — Linked daily journal **`Backlog candidates`** section + weekly **`Carry-over from journals`**; session scan skill and journaling rules.
- **2026-03-22** — Initial doc: merged traditional definitions (awork, Scrum), workspace working definition, three intake lanes, research touchpoints, five-layer capability backlog opinion, automation draft policy.
