# Agentic AI & LLM context — curated reading list

**Purpose:** Reputable and high-signal references on **context windows**, **long chats**, **memory**, **RAG**, and **IDE agent** practices — so humans can reason about *what* the model actually sees and *when* to fork a new thread.

**Companion (plain language):** [`onboarding/guides/working-with-ai-context.md`](../onboarding/guides/working-with-ai-context.md)

**Deep dive (technical):** [`ai-engineering/context-engineering.md`](../ai-engineering/context-engineering.md) — synthesized knowledge article with core concepts, principles, and practical takeaways

**Disclaimer:** Vendor docs change URLs; arXiv versions may update. Prefer official docs for integration decisions; papers for *why* behavior happens.

---

## A. Foundations — what “context” is

| # | Resource | Why it’s valuable |
|---|----------|-------------------|
| 1 | [Anthropic — Context windows](https://docs.anthropic.com/en/docs/build-with-claude/context-windows) | Clear definition: context = working memory; notes **linear growth**, **context rot**, compaction |
| 2 | [Anthropic — Compaction](https://docs.anthropic.com/en/docs/build-with-claude/compaction) | How **long-running** threads get **summarized** when near limits (agentic workflows) |
| 3 | [Anthropic — Prompt caching](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching) | Efficiency for **repeated** system/instruction prefixes (not human memory — engineering) |
| 4 | [Anthropic — Prompt engineering / Claude best practices](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/claude-4-best-practices) | Structure, clarity, **agentic** prompts — improves *use* of whatever context is visible |
| 5 | [OpenAI — Conversation state](https://platform.openai.com/docs/guides/conversation-state) | Stateful threads, **context window** billing, chaining responses |
| 6 | [OpenAI — Compaction (API)](https://developers.openai.com/api/docs/guides/compaction) | **Server-side** context reduction for long runs |

---

## B. Research — limits and failure modes

| # | Resource | Why it’s valuable |
|---|----------|-------------------|
| 7 | [Liu et al., *Lost in the Middle* (arXiv:2307.03172)](https://arxiv.org/abs/2307.03172) | Seminal **U-shaped** attention: evidence at **start/end** of context often easier than **middle** |
| 8 | [Lewis et al., *Retrieval-Augmented Generation* (arXiv:2005.11401)](https://arxiv.org/abs/2005.11401) | Foundational **RAG**: don’t stuff everything into the window — **retrieve** what matters |
| 9 | [*A Survey on the Memory Mechanism of LLM-based Agents* (arXiv:2404.13501)](https://arxiv.org/abs/2404.13501) | Taxonomy: **short-term** context vs **long-term** stores; agent memory design |
| 10 | [GWNET / OAJAIML — *Maximum Effective Context Window* (2024)](https://www.oajaiml.com/archive/context-is-what-you-need-the-maximum-effective-context-window-for-real-world-limits-of-llms) | Empirical gap: **advertised** vs **usable** context; degradation curves |
| 11 | [Zylos — LLM context management & long-context strategies (2026)](https://zylos.ai/research/2026-01-19-llm-context-management) | Practitioner-oriented synthesis: lost-in-middle, caching, tiers (third party — triangulate) |

---

## C. Practice — managing human ↔ agent collaboration

| # | Resource | Why it’s valuable |
|---|----------|-------------------|
| 12 | [Cursor — Rules (official)](https://cursor.com/docs/context/rules) | **Models don’t retain memory between completions**; rules = **persistent** prompt-level context |
| 13 | [Cursor — `llms.txt` / doc index](https://cursor.com/llms.txt) | Entry to current Cursor docs (rules, context, product behavior) |
| 14 | [*Field Guide to AI* — Context management](https://fieldguidetoai.com/guides/context-management) | Rolling windows, summarization, **memory systems** — vendor-agnostic framing |
| 15 | [Simon Willison — Long context in LLM 0.24 (fragments)](https://simonwillison.net/2025/Apr/7/long-context-llm) | Practitioner lens: **long context is powerful** but you still **engineer** what gets fed in |
| 16 | [Simon Willison — long-context tag](https://simonwillison.net/tags/long-context/) | Ongoing notes on model + tool ecosystem |

---

## D. Extended reading — agents, memory, mitigations

| # | Resource | Why it’s valuable |
|---|----------|-------------------|
| 17 | [*Memory in the Age of AI Agents* (arXiv:2512.13564)](https://arxiv.org/abs/2512.13564) | Recent survey-ish framing on **agent memory** |
| 18 | [*What Works for ‘Lost-in-the-Middle’?* (arXiv:2511.13900)](https://arxiv.org/abs/2511.13900) | Mitigations benchmark — shows **not** all fixes work uniformly |
| 19 | [*Lost in the Middle* follow-up (arXiv:2510.10276)](https://arxiv.org/abs/2510.10276) | Emergent IR perspective on the effect |
| 20 | [Industrial Logic — INVEST model (user stories)](https://www.industriallogic.com/blog/the-invest-model-for-user-stories/) | Adjacent: **small, testable** units of work ↔ smaller context per task (process, not LLM theory) |
| 21 | [Neo4j — GraphRAG introduction](https://neo4j.com/blog/genai-knowledge-graph-graphrag/) | Ecosystem: **graph + retrieval** as alternative to giant flat prompts (vendor blog — concept clear) |
| 22 | [LangChain — Short-term memory](https://docs.langchain.com/oss/python/langchain/short-term-memory) | Agents: **threads**, history, trimming when the window fills (framework docs) |

---

## E. Optional — product & narrative

| # | Resource | Why it’s valuable |
|---|----------|-------------------|
| 23 | [Anthropic — Introducing prompt caching (news)](https://www.anthropic.com/news/prompt-caching) | **Why** caching exists; cost/latency story |
| 24 | [Towards AI — *Context Window Paradox*](https://pub.towardsai.net/the-context-window-paradox-engineering-trade-offs-in-modern-llm-architecture-d22d8f954a05) | Trade-offs: bigger window ≠ uniformly better *(editorial — verify claims)* |
| 25 | [Towards AI — *Context engineering for AI coding agents*](https://pub.towardsai.net/context-engineering-for-ai-coding-why-your-200k-token-window-is-lying-to-you-67891d4a048e) | **Coding-agent** framing: selective context vs “dump the repo” |
| 26 | [Medium — Claude’s 1M context… until it isn’t](https://medium.com/@ai_transfer_lab/claudes-1m-context-window-looks-like-an-easy-win-until-it-isn-t-28ab39a9027d) | Cautionary lens on **huge** windows *(opinion piece)* |

---

## Quick numbers (rule of thumb, not a promise)

- **Recency bias:** Recent turns are usually “hotter” than very old turns unless summarized or re-injected.  
- **Effective vs. advertised:** Research and benchmarks often show **degradation before** the published token cap.  
- **Middle of dump:** Key facts buried **between** lots of other text can be **missed** — design docs and prompts accordingly (“lost in the middle”).  
- **Your repo beats your chat:** Git + `activeContext.md` + rules are **durable** context; chat is **ephemeral working set**.

---

*Last curated: 2026-03-25 — **26** entries (A–E); extend with org-specific MLOps / security guides as needed.*
