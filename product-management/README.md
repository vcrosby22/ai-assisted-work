# Product management (`product-management/`)

Workspace layer for **PM frameworks** used by Victoria (TPM/PM) and for **Cursor for PMs** content.

| File | Role |
|------|------|
| [`PM_KNOWLEDGE.md`](PM_KNOWLEDGE.md) | Indexed reference — software, hardware, UI, data, AI; **§6** = workspace ideation/strategy notes (e.g. defensibility) |
| [`BACKLOG_BEST_PRACTICES.md`](BACKLOG_BEST_PRACTICES.md) | Synthesized backlog best practices — DEEP, refinement, INVEST, prioritization frameworks, discovery vs delivery, story splitting; **not** your private backlog rows |
| [`PUBLIC_DOC_QUALITY_CRITERIA.md`](PUBLIC_DOC_QUALITY_CRITERIA.md) | Quality standard for every public file in this repo — nine criteria treating docs as products (audience, navigation, scannability, self-contained links) |
| [`GLOSSARY.md`](GLOSSARY.md) | Terms & definitions for **non-developer** readers; **Category (Parent outcome)** for future filters; **durable docs** defined; promote from journal **Glossary candidates**; evolve under **BL-29** |
| [`research/SOURCE_INDEX.md`](research/SOURCE_INDEX.md) | Canonical source list + harvest metadata; initial 27 URLs plus 2026-05-09 AI PM agent delta |
| [`research/2026-05-09-ai-pm-agent-resource-pack.md`](research/2026-05-09-ai-pm-agent-resource-pack.md) | Fresh 13-source resource pack for PM frameworks, context engineering, and AI PM agent design |
| [`research/2026-05-09-design-methodology-resource-pack.md`](research/2026-05-09-design-methodology-resource-pack.md) | Fresh 8-source pack for Design Thinking, UCD/HCD, Service Design, Service Blueprints, and Double Diamond |
| [`context/AI_PM_AGENT_CONTEXT.md`](context/AI_PM_AGENT_CONTEXT.md) | Agent-facing operating context: source hierarchy, required context packet, PM reasoning loop, guardrails, done criteria |
| [`workflows/AI_PM_WORKFLOWS.md`](workflows/AI_PM_WORKFLOWS.md) | Workflow router for strategy, discovery, prioritization, roadmapping, PRDs, delivery shaping, context engineering, and PM review |
| [`templates/PM_AGENT_TEMPLATES.md`](templates/PM_AGENT_TEMPLATES.md) | Reusable PM artifact templates: strategy brief, discovery brief, prioritization scorecard, roadmap, PRD, shaped pitch, context packet |

**Cursor:** rule `product-management.mdc` (glob), skill `product-management`, command `/pm`. **Always-on:** rule `non-technical-documentation.mdc` (plain language + glossary habit). **Skill:** `non-technical-glossary-capture` (journal / session-end).

**Contrast:** **`pmo/PMO_KNOWLEDGE.md`** — project/program delivery, PMO, Lean/Six Sigma/CRISP-DM (`/pmo`).

Hydration policy: prefer **adding to `SOURCE_INDEX.md`**, then **synthesize** into `PM_KNOWLEDGE.md` — avoid unvetted scrapes.

## AI PM agent quick start

For any agent doing product-management work:

1. Read [`context/AI_PM_AGENT_CONTEXT.md`](context/AI_PM_AGENT_CONTEXT.md).
2. Route the task through [`workflows/AI_PM_WORKFLOWS.md`](workflows/AI_PM_WORKFLOWS.md).
3. Use the smallest relevant template from [`templates/PM_AGENT_TEMPLATES.md`](templates/PM_AGENT_TEMPLATES.md).
4. For design-methodology work, load [`research/2026-05-09-design-methodology-resource-pack.md`](research/2026-05-09-design-methodology-resource-pack.md).
5. Cite source provenance from [`research/SOURCE_INDEX.md`](research/SOURCE_INDEX.md) or the relevant 2026-05-09 resource pack.
