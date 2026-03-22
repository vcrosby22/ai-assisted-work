# AI Engineering — technical knowledge base

A curated, scholarly knowledge base for **practitioners and power users** who want to understand the research, architecture, and tooling behind large language models (LLMs), agentic AI, and modern AI systems.

**Who this is for:** Engineers, technical PMs, researchers, and advanced Cursor users who want primary sources — not summaries of summaries. If you're looking for a gentler introduction, start with [`onboarding/`](../onboarding/).

---

## Topic map

| Article | What it covers | Sources |
|---------|---------------|---------|
| [**Context engineering**](context-engineering.md) | The discipline of designing what an LLM sees at inference time — beyond prompt engineering to the full information pipeline | ~12 |
| [**LLM foundations**](llm-foundations.md) | Transformer architecture, training paradigms, scaling laws, and the key papers that define the field | ~12 |
| [**Agentic AI**](agentic-ai.md) | Agent architectures, tool use, planning, memory, multi-agent systems, and the research frontier | ~12 |
| [**Full-stack LLM development**](full-stack-llm.md) | Fine-tuning, inference serving, evaluation, deployment, and production engineering | ~10 |
| [**AI services and APIs**](ai-services-and-apis.md) | Commercial and open-source model APIs, comparison frameworks, security, and governance | ~8 |

**Master bibliography:** [SOURCE_INDEX.md](SOURCE_INDEX.md) — every URL across all articles in one place with metadata.

---

## How to use this section

**If you're building with LLMs:** Start with [context engineering](context-engineering.md) and [full-stack LLM](full-stack-llm.md) — they cover the decisions you'll face daily.

**If you're evaluating AI strategy:** Read [AI services and APIs](ai-services-and-apis.md) for the commercial landscape, then [LLM foundations](llm-foundations.md) for the "why" behind model capabilities.

**If you're researching agents:** [Agentic AI](agentic-ai.md) collects the foundational papers and emerging architectures.

**If you want the raw reading list:** [SOURCE_INDEX.md](SOURCE_INDEX.md) has every source with domain, category, and year.

---

## Source standards

Every source in this section meets at least one of these criteria:

- **Primary research** — published on arXiv, in peer-reviewed venues (NeurIPS, ICML, ACL, TMLR), or as official technical reports
- **Official vendor documentation** — Anthropic, OpenAI, Google, Meta, Hugging Face
- **Established practitioners** — Lilian Weng, Chip Huyen, Andrej Karpathy, Simon Willison, Jay Alammar
- **Recognized standards bodies** — NIST, OWASP, EU AI Act

Blog posts and opinion pieces are included only when they offer unique practitioner insight not available elsewhere. They are marked as such.

---

## Related areas in this repo

| Area | Where | Audience |
|------|-------|----------|
| AI context (quick reading list) | [`cursor-knowledge/ai-context-reading-list.md`](../cursor-knowledge/ai-context-reading-list.md) | 26-link companion list for the onboarding guides |
| Non-technical AI onboarding | [`onboarding/`](../onboarding/) | Beginners and non-developers |
| PM knowledge and glossary | [`product-management/`](../product-management/) | Product managers and non-technical readers |
| Session log (build diary) | [`session-log.md`](../session-log.md) | Seeing real Cursor sessions in action |
