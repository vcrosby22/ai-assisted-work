# Session log — what was built and what was learned

This is the maintainer's **build diary**: real Cursor sessions showing what was built, which technologies were used, architecture decisions, and lessons learned along the way. It's not a tutorial — it's a window into how one person actually uses Cursor for real work.

> **Looking for guides instead?** Start with the [onboarding folder](onboarding/) or the [README](README.md).

---

## Session: 2026-03-13 — Foundation Build

### Use Case: Building a Complete Cursor Foundation

**What we solved:** Set up a "foundationally correct" Cursor environment covering all 16 areas: context, rules (4 types), skills, commands, hooks, MCP, journal, profiles, knowledge base, notepads, activeContext, AGENTS.md, indexing, GitHub, and shareable templates.

**Why it matters:** Without persistent context and structured guidance, every Cursor session starts cold. This foundation ensures the agent knows its role, remembers past sessions, and captures knowledge automatically.

### Technologies

- **Cursor Rules** (`.cursor/rules/*.mdc`) — YAML frontmatter + Markdown; 4 types: always-apply, agent-decides, globs, manual
- **Cursor Commands** (`.cursor/commands/*.md`) — reusable `/` workflows
- **Cursor Hooks** (`.cursor/hooks.json` + shell scripts) — event-driven automation
- **Cursor Skills** (`.cursor/skills/` or `~/.cursor/skills/`) — portable agent capability packages
- **Memory Bank pattern** — structured Markdown files for persistent context across sessions
- **Timo Bakx journaling template** — `journal/YEAR/WEEK/` structure with AI Coach rules

### Architecture Decisions

| Decision | Choice | Reasoning |
|----------|--------|-----------|
| Rule types | Always: core, AI coach, journaling, security. Agent-decides: reflection. | Core behavior should never be skipped; reflection is contextual |
| Journal scope | Both personal growth and builder log | The user is both growing professionally and building things — capture both |
| Journal location | Same repo as code projects | User wants one repo on GitHub; journal benefits from being next to code |
| Session continuity | `activeContext.md` at project root | Simpler than full Memory Bank; one file the agent reads first each session |

### Lessons Learned

- **Start with rules, not skills.** Rules define who the agent is and how it behaves. Skills are capabilities you add once you know what you need.
- **The "right context at the right time" principle** applies to everything: always-on rules for non-negotiables, agent-decides for domain context, commands for explicit workflows, hooks for automation.
- **Don't over-structure the journal.** The AI can find things by meaning. Keep templates light and let entries be freeform.
- **`.cursorignore` matters.** Excluding `node_modules/`, lock files, and large assets dramatically improves indexing speed and AI accuracy.
- **Community sources are invaluable.** Timo Bakx (journaling template), Theodoros Kokosioulis (rules/commands/skills/hooks guide), Nina (smart notebook), and the Cursor forum all contributed ideas.
- **Design for the relationship, not just the output.** The most important question a user can ask is "how can I help you work better with me?" This shifts the dynamic from tool-use to collaboration. Build it into the system (skill + command) so it's not a one-time conversation.

### Use Case: Collaboration Health Skill

**What we solved:** Created a `working-well-together` skill and `/collaboration-check` command that make the user-agent relationship a first-class concern — not an afterthought.

**Why it matters:** The agent performs best when it has current context, clear intent, honest feedback, and permission to push back. The user benefits most when the agent has memory, honesty, proactive capture, appropriate pace, and celebrates wins. Without making these explicit, both sides guess at what the other needs.

**How it works:** The skill defines what the agent needs (context, intent, feedback, permission, space) and what the user needs (memory, honesty, capture, pace, celebration). The `/collaboration-check` command runs a quick health check any time. The skill is also auto-loaded when the agent senses things are off or when the user asks "how can I help you?"

---

## Session: 2026-03-13 — Context Engineering Research

### What is Context Engineering?

**Definition:** Context engineering is the systematic process of designing, building, and optimizing the entire information environment that an AI agent operates within. It goes beyond prompt engineering to encompass the complete data pipeline that determines what information an AI model sees before generating a response.

**Origin:** The term gained traction in mid-2025. [Shopify CEO Tobi Lutke](https://simonwillison.net/2025/Jun/27/context-engineering): "the art of providing all the context for the task to be plausibly solvable by the LLM." [Andrej Karpathy](https://pureai.com/articles/2025/09/23/karpathy-puts-context-at-the-core-of-ai-coding.aspx): "the delicate art and science of filling the context window with just the right information for the next step."

**Why it matters:** Over 40% of AI project failures stem from poor or irrelevant context, not flawed models. A Feb 2026 peer-reviewed study (9,649 experiments) confirmed context quality matters more than prompt phrasing. Structured context reduces hallucination rates by 40%+ (Anthropic research).

### The Five-Layer Architecture

| Layer | What | Our Implementation |
|-------|------|-------------------|
| A: System Identity | Role, reasoning behavior, constraints | `philosophy.mdc`, `ai-coach-role.mdc`, `ai-coach-personality.mdc` |
| B: Knowledge Retrieval | Selective information from knowledge stores | Cursor's built-in indexing + `.cursorignore` optimization |
| C: Short-term Memory | Conversation history, intermediate results | Chat context + `activeContext.md` |
| D: Long-term Memory | Facts across sessions, decisions, patterns | This repo: `session-log.md` — optional private monorepo extras: `journal/`, `agent-log/`, `profile` |
| E: Tools & Output | Tool definitions, available actions | `.cursor/commands/`, `.cursor/skills/`, `.cursor/hooks.json` |

### The Token Tax Problem

Every always-apply rule consumes tokens on every request. A 100-line rule costs 500-1,000 tokens per interaction. Our current always-apply rules:

| Rule | Est. Tokens | Necessity |
|------|-------------|-----------|
| `philosophy.mdc` | ~200 | Essential (compressed from ~350) |
| `ai-coach-role.mdc` | ~400 | Essential |
| `ai-coach-personality.mdc` | ~200 | Review — could merge into role |
| `journaling-rules.mdc` | ~350 | Review — could be agent-decides or globs |
| `general-rules.mdc` | ~300 | Essential |
| `security.mdc` | ~150 | Essential |
| `cursor-knowledge.mdc` | ~150 | Essential |
| **Total always-on** | **~1,750** | **Audit needed** |

### Key Principles for Our Setup

1. **Precision beats volume.** The goal isn't to give the AI more information — it's the right information. Selectively loading the most relevant 10-30% of available data improves accuracy AND reduces cost.
2. **"Lost in the middle" problem.** LLMs pay disproportionate attention to information at the beginning and end of context. Critical details in the middle get overlooked. Put important things first and last.
3. **Modular rules with globs.** Rules that only apply to specific file types (via glob patterns) save tokens compared to always-apply rules. Convert non-essential always-apply rules.
4. **Lazy context loading.** Load only data actively needed rather than everything upfront. Skills and agent-decides rules do this naturally — they load only when relevant.
5. **Audit regularly.** Token costs compound. Review which rules are always-on and whether they need to be.

### Lessons Learned

- **We were already doing context engineering.** Every rule, activeContext update, agent-log entry, and .cursorignore exclusion is context engineering. The discipline gives it a name and a science.
- **The philosophy.mdc compression (32 lines to 15) was context engineering in action.** Same meaning, 40% fewer tokens, full text available on demand in OUR-PHILOSOPHY.md.
- **agent-log/what-i-need.md is a context engineering artifact.** It tells the next session exactly what's missing — addressing the "context gap" problem directly.
- **Some of our always-apply rules may not need to be always-apply.** `journaling-rules.mdc` could be globs-scoped to `journal/**/*.md`. `ai-coach-personality.mdc` could merge into `ai-coach-role.mdc`. This is a future optimization task.

---

## Session: 2026-03-17 to 2026-03-19 — Financial Agent Build

### Use Case: Building a Personal Financial Analysis Agent

**What we solved:** Built a multi-layered financial analysis system that pulls real market data, runs rule-based risk assessment, and uses Claude for intelligent analysis — with honest confidence scoring and documented limitations.

**Why it matters:** The knowledge base serves both learning and working analysis. Risk mitigation elevated the system from a basic prototype to something with honest uncertainty acknowledgment.

### Technologies

| Technology | Purpose | Notes |
|-----------|---------|-------|
| **Python 3.12** (Anaconda) | Core language | System Python was 3.9; needed 3.10+ for type hints and Pydantic v2 |
| **yfinance** | Stock, ETF, index, forex data | Free, unofficial Yahoo Finance scraper — no SLA |
| **ccxt** (Coinbase) | Crypto data | Binance blocked by georestriction; Coinbase worked with symbol remapping |
| **fredapi** | Macroeconomic indicators (FRED) | Free API key; 7 series: yield curves, credit spreads, unemployment, etc. |
| **Anthropic Claude** (claude-sonnet-4-20250514) | AI-powered market analysis | Hardened system prompt with uncertainty requirements |
| **SQLAlchemy + SQLite** | Persistent storage | Market snapshots, analysis reports, alerts, predictions |
| **rich** | CLI formatting | Tables, panels, colored output |
| **Pydantic + pydantic-settings** | Config management | .env loading, typed settings |

### Architecture Decisions

| Decision | Choice | Reasoning |
|----------|--------|-----------|
| Risk engine layers | 3 layers: technical (lagging) + macro (leading) + fundamental (leading) | Single-layer technical analysis misses slow deterioration and macro shifts |
| Leading indicator weight | 1.5x multiplier over lagging | Leading indicators (yield curve, earnings revisions) predict; lagging indicators (RSI, MA) confirm |
| Confidence scoring | Based on data source count + leading signal count | "CRITICAL with LOW confidence" is fundamentally different from "CRITICAL with HIGH confidence" |
| Position sizing | Mandatory guardrail on every output | Even correct analysis is dangerous without position limits |
| Prediction tracking | Log and measure at 7/30/60/90 days | Creates accountability and a feedback loop — shows which signals actually predict |
| Limitations | Documented in knowledge base + every CLI output | Honesty about what the system can't do is as important as what it can |
| Data completeness note | Injected into Claude prompt | Tells Claude what data it has and what's missing so it can calibrate confidence |

### Key Patterns

**3-Layer Risk Assessment:**
```
Layer 1: Technical (lagging) — VIX, death crosses, RSI, breadth, treasury yields
Layer 2: Macro (leading) — yield curve, credit spreads, unemployment, consumer confidence, Fed
Layer 3: Fundamental (leading) — EPS revisions, insider activity, analyst targets, financial health
```

**Confidence Calibration:**
- High confidence: 3+ data sources present, 2+ leading signals
- Medium confidence: 2 data sources OR 1+ leading signals
- Low confidence: Technical data only, no leading signals

**Position Sizing Guardrails:**
- Low risk (1-3): 3-5% of portfolio, stop-loss 10-15%
- Medium risk (4-6): 1-3% of portfolio, stop-loss 8-10%
- High risk (7-10): 0.5-1% of portfolio, stop-loss 5-8%
- Any short: 1% max, defined buy-stop
- Critical market risk: Cash only, no new positions

### Lessons Learned

- **"How good is this really?" is the most valuable question.** Pushing for honest risk assessment led to identifying weaknesses and implementing mitigations. The system went from single-layer technical to 3-layer with confidence scoring.
- **Free data can be institutional-grade if layered correctly.** yfinance (technical) + FRED (macro) + yfinance fundamentals (earnings/insider) covers the same categories as Bloomberg terminals — just with less granularity and no SLA.
- **Leading vs. lagging is a fundamental distinction.** Most retail tools only show lagging indicators (RSI, moving averages). Adding FRED macro data and earnings revisions gives forward-looking signals. Weighting them higher reflects their greater predictive value.
- **Consumer confidence at recessionary levels while hard data is fine** — this was the first real finding from the macro layer. It shows why macro data matters: sentiment can lead reality by months.
- **Confidence labels change decision-making.** "CRITICAL risk, MEDIUM confidence" means "take seriously but acknowledge gaps." Without the confidence label, every CRITICAL looks the same.
- **Document limitations honestly.** Three things the system can never fully solve: black swans, correlation breakdown in crises, and free data quality. Documenting these isn't weakness — it's calibration.
- **The VIX drop bug was instructive.** VIX drops are positive (fear decreasing), but the generic "large drop" check flagged them as negative. Domain knowledge matters — generic rules need domain-specific exceptions.
- **Build the prediction tracker early.** Even before you have accuracy data, the logging discipline forces the system to commit to predictions that can be verified. Accountability from day one.
- **Prompt hardening is cheap and high-impact.** Adding "state what data is missing" and "rate your own confidence" to Claude's system prompt costs nothing but significantly reduces false confidence in outputs.

### Use Case: Static HTML Financial Report

**What we solved:** Built a static HTML report generator instead of a live dashboard. One Python script collects data, runs analysis, screens opportunities, and generates a self-contained HTML file that opens in the browser.

**Why it matters:** Zero running costs, no server, no dependencies at runtime. Generates in ~35 seconds. The user gets a complete market briefing they can save, share, or reference offline.

### Technologies (additions)

| Technology | Purpose | Notes |
|-----------|---------|-------|
| **Static HTML generation** | Report output | Python f-strings building HTML — no template engine needed at this scale |
| **CSS `<details>/<summary>`** | Collapsible sections | Native HTML, no JavaScript required |

### Architecture Decisions (additions)

| Decision | Choice | Reasoning |
|----------|--------|-----------|
| Report format | Static HTML over live dashboard | Zero cost, no server, sufficient for current use. Live dashboard is premature optimization |
| Collapsible sections | `<details>/<summary>` with inline summaries | Reduces page scroll dramatically; inline signal counts in headers enable triage without expanding |
| Opportunity framing | "Risk-adjusted potential" not "low risk/high yield" | Honest framing — every return carries commensurate risk; language shapes decision-making |
| Market coverage | Sector ETFs over individual stock expansion | One ETF per sector captures aggregate trends of hundreds of stocks efficiently |
| Opportunities default open | Only section open by default in HTML | Most actionable content should be visible immediately; data tables can be explored on demand |

### Lessons Learned (additions)

- **Static beats live for v1.** A static HTML file is the right first output. It can be generated on-demand, saved, compared across dates, and requires zero infrastructure. Move to live only when real-time updates have clear value.
- **Sector ETFs are the 80/20 of market coverage.** 11 SPDR Select Sector ETFs cover the entire economy. Adding them took 2 minutes of config and immediately surfaced sector rotation insights the system couldn't see before.
- **Inline summaries in collapsible headers are high-value UX.** Showing "Macro — 2 critical, 1 warning" in the header lets users triage without expanding. The summary IS the insight for most users; the detail is for deep-diving.
- **f-string HTML generation works surprisingly well at this scale.** No need for Jinja2 or a template engine when the HTML structure is predictable. Functions per section keep it modular. Only consider templates when the rendering logic gets complex or when non-developers need to edit templates.
- **Watchlist curation matters more than size.** Going from 10 mega-caps to 26 stocks + 17 ETFs meaningfully expanded coverage, but each addition was deliberate (mid-cap growth, small-cap disruptors, sector ETFs). Random expansion adds noise.
