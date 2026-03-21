# Product management knowledge base

Synthesized reference for **software, hardware, UI/UX, data-intensive, and AI/ML** product work. This file is **not** legal advice; EU AI Act and similar entries are pointers for **compliance awareness** — verify with counsel.

**Canonical URL list:** [`research/SOURCE_INDEX.md`](research/SOURCE_INDEX.md) (27 sources, harvested 2026-03-19).

---

## 0. How to use this KB

| When you need… | Start with sections… |
|----------------|----------------------|
| Org model, empowerment, discovery cadence | §1 Traditional / software |
| Physical product, gates, long-cycle NPD | §2 Hardware / NPD |
| UX strategy, design process, JTBD vs personas | §3 UI / UX |
| Metrics, prioritization scores, roadmaps | §4 Data, prioritization, roadmaps |
| ML viability, responsible AI, LLM security, regulation | §5 AI / ML |
| Product idea framing, defensibility, what to optimize for first | §6 Ideation & strategy vocabulary |
| **Backlog hygiene** — ordering, refinement, DEEP/INVEST, discovery vs delivery | §7 Backlog management |
| Plain definitions, acronyms, non-developer onboarding vocabulary; **Category** for user-outcome filtering | [`GLOSSARY.md`](GLOSSARY.md) |

**Changelog:** 2026-03-20 — **§7 Backlog management** (workspace Purpose → Epic → Story, DEEP/refinement pointers). 2026-03-20 — GLOSSARY: **Parent outcome** categories + **BL-29**. Link to `GLOSSARY.md` for terms sheet. §6 workspace capture (ideation example, defensibility, choice lenses). 2026-03-19 — Initial synthesis from 27 web sources (`SOURCE_INDEX.md`).

---

## 1. Traditional software product management

### 1.1 Empowered teams vs “IT mindset”

Strong product orgs orient teams to **serve customers in ways that meet business needs**, not merely “serve the business” with feature lists. Empowerment depends on **trust**, **leadership** (vision, strategy, principles, priorities, evangelism), and **management** (staffing, coaching, velocity of learning). OKRs often express org-level priorities; teams should be **missionaries**, not mercenaries.

*Sources: [SVPG – Empowered product teams](https://svpg.com/empowered-product-teams)*

### 1.2 Product discovery (why scheduling it like construction fails)

Discovery validates **real demand** and a solution that is **usable, useful, and feasible**. Treating discovery as a fixed calendar phase ignores that invention is **creative** and nonlinear; teams must **change course** from evidence. Faster discovery reduces wasted engineering on expensive “production prototypes.”

*Sources: [SVPG – Product discovery](https://svpg.com/product-discovery)*

### 1.3 Dual-track agile → continuous discovery + delivery

**Discovery** generates validated backlog items; **delivery** ships releasable software. Prefer **collaboration** (PM + design + engineering) over mini-waterfalls of handoffs. Validate **before** production code when possible (“fake it before you make it”). Cagan later emphasizes **continuous discovery** and **continuous delivery** over over-focusing on the “dual-track” label; many teams blend Scrum timeboxing with **Kanban**-style continuous flow.

*Sources: [SVPG – Dual-Track Agile](https://svpg.com/dual-track-agile), [SVPG – Continuous discovery](https://www.svpg.com/continuous-discovery/)*

### 1.4 Shape Up (fixed cycles, betting table)

Basecamp’s **Shape Up** caps risk with **appetite** (time budget), **shaping** work before commitment, and **cool-down** — an alternative to backlog thrash and infinite estimation. Full method is book-length; use when teams need **strategic resource bets** rather than passive queue ordering.

*Sources: [Shape Up](https://basecamp.com/shapeup)*

### 1.5 Lean Startup: validated learning and MVP

Startups (and intrapreneurial teams) should treat effort as **experiments**: “Should this be built?” and “Can we build a sustainable business?” **Build–measure–learn**, **MVP**, and **pivot/persevere** decisions reduce stealth development without customer contact. **Validated learning** is the unit of progress under uncertainty.

*Sources: [Lean Startup – Methodology](https://theleanstartup.com/principles), [Wikipedia – MVP](https://en.wikipedia.org/wiki/Minimum_viable_product)*

### 1.6 User stories and narrative backlog

**User story mapping** orders the **user’s journey** horizontally and release slices vertically — avoiding pure feature arguments and anchoring backlog to **outcomes** along a narrative.

*Sources: [Jeff Patton – User story mapping](https://jpattonassociates.com/user-story-mapping/)*

---

## 2. Hardware and classical NPD

### 2.1 New product development (NPD) structure

NPD spans **fuzzy front-end** (ideation, opportunity analysis through pre-technical evaluation), **design**, **implementation/verification**, and **commercialization**. Complex engineered goods (aerospace, automotive) often use **integrated product teams**, long horizons, and heavy **design–manufacturing** coupling (QFD, DFM/DFA).

*Sources: [Wikipedia – New product development](https://en.wikipedia.org/wiki/New_product_development)*

### 2.2 Phase-gate (stage-gate) governance

Work breaks into **phases** separated by **gates**: go/kill and prioritization based on business case, risk, and resources. Effective gates use **clear criteria** (must/should meet) and portfolio discipline (“gates with teeth”). Tradeoff: structure aids oversight but can **dampen creativity** if misapplied.

*Sources: [Wikipedia – Phase-gate process](https://en.wikipedia.org/wiki/Phase-gate_process)*

**PM takeaway:** Software teams borrow gate **thinking** for regulated devices (medical, auto); pair with **Lean/Agile** execution inside phases where allowed.

---

## 3. UI / UX–centric product work

### 3.1 UX roadmaps (Now / Next / Future)

A **UX roadmap** is a **living strategic artifact**: beneficiary + need, **business outcome**, owner, themes across **Now / Next / Future**. Distinguish from **release plans** (features/dates), **Kanban** execution boards, **backlogs** (delivery granularity), and **customer-journey maps** (as-is experience research).

*Sources: [NN/g – UX roadmaps](https://www.nngroup.com/articles/ux-roadmaps/)*

### 3.2 Design thinking (six phases)

IDEO/Nielsen Norman distillation: **empathize, define, ideate, prototype, test, implement** within buckets **understand → explore → materialize**. Process is **iterative**, not strictly linear; **implementation** is often neglected — “more design doing.”

*Sources: [NN/g – Design thinking 101](https://www.nngroup.com/articles/design-thinking/)*

### 3.3 Jobs-to-be-done vs personas

**JTBD** frames needs as **outcomes** users hire products to achieve; strong **personas** embed behavioral, attitudinal, and goal data — not only demographics. JTBD alone may underweight **empathy** and **segment tradeoffs**; combined use is common.

*Sources: [HBR – Jobs to be done](https://hbr.org/2016/09/know-your-customers-jobs-to-be-done), [NN/g – Personas vs JTBD](https://www.nngroup.com/articles/personas-jobs-be-done/)*

---

## 4. Data-rich product: metrics, prioritization, roadmaps

### 4.1 RICE prioritization

**RICE = Reach × Impact × Confidence ÷ Effort** (Intercom). Forces explicit **reach** estimates, **impact** tiering, **confidence** percentage, and **person-month** effort; produces comparable **impact per effort** scores — still subject to judgment and dependencies.

*Sources: [Intercom – RICE](https://www.intercom.com/blog/rice-simple-prioritization-for-product-managers/)*

### 4.2 Kano model

Classifies features into **Must-be**, **One-dimensional**, **Attractive**, **Indifferent**, **Reverse** quality; attributes **drift** over time (delighters become basics). Supports survey-driven prioritization and QFD linkage.

*Sources: [Wikipedia – Kano model](https://en.wikipedia.org/wiki/Kano_model)*

### 4.3 MoSCoW

**Must / Should / Could / Won’t (this time)** for timeboxed delivery; pairs with **MVP/MMF** scoping. Criticisms: politics, ambiguity on “won’t,” weak rationales across items.

*Sources: [Wikipedia – MoSCoW](https://en.wikipedia.org/wiki/MoSCoW_method)*

### 4.4 Opportunity solution trees (OST)

Visual link: **outcome** (business) → **opportunities** (customer needs) → **solutions** → **assumption tests**. Operates in **continuous discovery** with **product trio**. Prerequisites: customer interviews, clear outcome, value-prop theory.

*Sources: [Product Talk – Opportunity solution trees](https://www.producttalk.org/2021/04/opportunity-solution-trees/)*

### 4.5 North Star metric & “three games”

**North Star** = one **leading** metric expressing **customer value** and **strategy** (Amplitude). Avoid vanity metrics (e.g. raw DAU) if they don’t reflect value. Categorize product “game”: **Attention**, **Transaction**, or **Productivity** to choose coherent North Stars; use **input metrics** (tree) for alignment.

*Sources: [Amplitude – North Star](https://amplitude.com/blog/product-north-star-metric)*

### 4.6 OKRs

**Objectives** (qualitative, directional) + **3–5 measurable key results**; Grove/Intel heritage; Google popularization. Targets often **aspirational ~70%** hit rate; avoid BAU-as-OKR and individual OKRs that become task lists.

*Sources: [Wikipedia – OKR](https://en.wikipedia.org/wiki/OKR)*

### 4.7 Product roadmaps (general)

Roadmaps communicate **vision, direction, priorities, progress**; audience-specific views for **dev, execs, sales, customers**; tie items to **strategy**; update cadence balances accuracy vs overhead. Differentiate roadmap (why/what problems) from delivery plans (how/when features).

*Sources: [Atlassian – Product roadmap](https://www.atlassian.com/agile/product-management/product-roadmaps), [ProductPlan – What is a roadmap](https://www.productplan.com/learn/what-is-a-product-roadmap/)*

---

## 5. AI / ML product management

### 5.1 Rules of ML: product judgment before models

Google’s guidance: most wins are **engineering and features**, not exotic algorithms. **Don’t ship ML** until simple **heuristics** are insufficient; keep **pipelines solid**, add **commonsense features**, pick a **reasonable objective**, validate **end-to-end**. Terminology: **pipeline, objective, metric, model, labels, skew**.

*Sources: [Google – Rules of ML](https://developers.google.com/machine-learning/guides/rules-of-ml)*

### 5.2 NIST AI RMF (governance lens)

Voluntary **AI RMF** for trustworthy AI: functions **Govern, Map, Measure, Manage**; trustworthiness includes validity/reliability, safety, security/resilience, accountability/transparency, explainability, privacy, fairness/bias. Use for **risk registers** and cross-functional alignment.

*Sources: [NIST – AI RMF](https://www.nist.gov/itl/ai-risk-management-framework)*

### 5.3 OWASP Top 10 for LLM applications

High-risk classes for LLM products (versions evolve): **prompt injection**, **insecure output handling**, **training/poisoning**, **denial of service**, **supply chain**, **sensitive disclosure**, **plugins/tools**, **excessive agency**, **overreliance**, **model theft** (2023/24 list on project page). **GenAI hub** hosts updated Top 10 material (e.g., 2025 taxonomy).

*Sources: [OWASP LLM Top 10 project](https://owasp.org/www-project-top-10-for-large-language-model-applications/), [OWASP GenAI – LLM Top 10](https://genai.owasp.org/llm-top-10/)*

### 5.4 EU AI Act (regulatory pointer)

EU regulation **2024/1689** — risk-based obligations for AI in market. PMs need **awareness** of prohibited/high-risk categories, documentation, and timeline; **official text** via EUR-Lex and reputable summaries.

*Sources: [EU AI Act hub](https://artificialintelligenceact.eu/the-act/)*

---

## 6. Ideation & strategy vocabulary (workspace capture)

*This section is **Victoria + assistant session notes**, not third-party synthesis. For vetted links, add to [`research/SOURCE_INDEX.md`](research/SOURCE_INDEX.md) before treating claims as externally sourced.*

### 6.1 Illustrative product direction (hypothetical, 2026-03-20)

One concrete shape worth prototyping mentally: a **decision log with scheduled, low-noise review** — users record **what** they decided, **why**, and **what would change their mind**; the product **nudges** on a cadence they control and surfaces **when reality diverges** (prices, deadlines, assumptions) rather than pushing endless capture.

- **Core loop:** log → time passes → compare to reality → adjust.
- **Why it’s interesting:** many tools optimize **ingestion**; fewer help **revisit with discipline** without shame or notification spam. Pattern applies across investing, hiring, health tradeoffs, and product bets.
- **Form factor:** boring tech; **PWA** if web-first; **mobile-first** if notifications/widgets are the habit anchor.
- **“Moat” honesty:** often **trust + calm UX + retention**, not a secret algorithm — viable if a niche is owned.

### 6.2 Defensibility (strategy / competition)

**Defensibility** = how hard it is for someone else to **copy what you shipped** and take your **users or margin** after you’ve proven the idea works. It is **not** the same as “clean code,” a patent on everything, or (in security) a **defensible system** / reduced attack surface — use *security posture* for that meaning.

**Common sources of defensibility** (often combined):

| Source | Plain language |
|--------|----------------|
| **Distribution** | You’re already where buyers/users are (community, SEO, partnerships, brand, sales motion). |
| **Data / network** | Product improves or sticks with usage — *often overstated* unless data is exclusive and compounding. |
| **Workflow lock-in** | Deep integration into how people work; switching cost is real. |
| **Trust, compliance, reliability** | Especially in regulated or high-stakes domains. |
| **Economies of scale** | Unit economics or quality a clone can’t match without matching volume. |

**PM honesty for small products:** many are defensible mainly through **brand + distribution + retention** in a **focused niche** — that can be enough.

### 6.3 Lenses when choosing what to build (answers personal)

Useful forcing questions (not mutually exclusive):

1. **Time to first user** — how fast a credible slice reaches someone who cares.
2. **Defensibility** — what remains yours if a well-funded team ships the same headline tomorrow (§6.2).
3. **Personal itch** — whether you’ll sustain energy through implementation and maintenance.

*Victoria (2026-03-20): questions resonated; prioritization across these lenses still TBD.*

---

## 7. Backlog management (hygiene, shape, and this workspace)

**Why this section:** Product backlogs fail when they are unordered junk drawers. Industry practice emphasizes **ordering**, **refinement**, and **right-sized** items near the top — without pretending the far future is fully specified.

### 7.1 Themes from standard practice

- **Ordered backlog** — The product backlog is a single ordered list (Scrum Guide). “Priority” is expressed by **position** and explicit rank fields (e.g. P0–P3) where useful.
- **DEEP** — Often summarized as *detailed appropriately, emergent, estimated, prioritised* (Roman Pichler and others). Near-term items gain detail through **refinement**; distant items stay coarse until they surface.
- **Refinement loop** — Regularly clarify scope, split large items, and prepare upcoming work so planning is cheap. Collaboration between product and delivery reduces late surprises.
- **Stories and INVEST** — Small, valuable backlog items benefit from **INVEST**-style quality (independent, negotiable, valuable, estimable, small, testable) and **splitting** when one card hides multiple goals or too much risk.
- **Discovery vs delivery** — Some teams separate **opportunity / discovery** work from **committed build** items so they validate problems before over-investing (see SVPG “opportunity backlog” framing in the reading list below).

### 7.2 How `where_cursor_feels_home` implements this

This workspace uses **markdown as source of truth** with a strict hierarchy:

1. **Purpose** (`PU-NN`) — *Why* a strand of work exists (strategic outcome / north-star bucket).
2. **Epic** (`EP-NN`) — Theme under one Purpose; every story rolls up through exactly one Epic.
3. **Story** — **`BL-##`** row in [`BACKLOG.md`](../../BACKLOG.md) (**Title** = required) plus optional narrative in [`BACKLOG_STORY_DETAILS.md`](../../BACKLOG_STORY_DETAILS.md); optional rich file in [`backlog/tickets/`](../../backlog/tickets/) (`TKT-NNNNN`).

**Required on a story:** **title** + **epic** (which implies **purpose** via [`backlog/EPIC_REGISTRY.md`](../../backlog/EPIC_REGISTRY.md)). **Description** is encouraged for refinement but **not required** in the ticketing template.

**Curated reading list (13+ URLs):** [`BACKLOG_PRODUCT_PRACTICES_URLS.md`](../../cursor-knowledge/BACKLOG_PRODUCT_PRACTICES_URLS.md) — Scrum Guide, refinement, Pichler, SVPG, INVEST, story splitting.

**Workspace specs:** [`BACKLOG_HIERARCHY.md`](../../BACKLOG_HIERARCHY.md) · [`backlog/TICKETING_MODEL.md`](../../backlog/TICKETING_MODEL.md) · [`backlog/PURPOSE_REGISTRY.md`](../../backlog/PURPOSE_REGISTRY.md).

---

## 8. Cross-domain cheat sheet

| Problem | Consider |
|--------|----------|
| Stakeholders want date-certain features | Separate **roadmap** (outcomes) from **release plan**; use confidence labels (NN/g). |
| Backlog fights | RICE or MoSCoW + **Kano** for delight vs table stakes. |
| Strategy drift | **North Star** + **OKRs** + OST for discovery traceability. |
| Hardware + software SKU | **Phase-gate** where regulated + **dual-track** inside phases for firmware/app. |
| “We need AI” | **Rules of ML** gate: heuristics first; NIST/OWASP for risk & security. |

---

## 9. Gaps for future hydration

- **Amazon Working Backwards / PR-FAQ** (primary AWS sources)
- **Data mesh / data product** paradigms (internal data platforms)
- **Outcome-based roadmap** (Product Talk) deep links beyond OST
- **Accessibility-specific PM** (WCAG-driven prioritization)
- **Industry regs** FDA SaMD, automotive SPICE (where relevant)

Record new URLs in [`research/SOURCE_INDEX.md`](research/SOURCE_INDEX.md) before merging claims into this file.
