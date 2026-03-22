# Context engineering

## At a glance

=== "Beginner"

    Context engineering is about giving an AI assistant the **right information at the right time** — like preparing a focused briefing packet before a meeting instead of dumping every document on the table. When you write clear instructions, open the right folder, or start a fresh chat for a new topic, you're already doing context engineering.

=== "Intermediate"

    The discipline of designing what an LLM sees at inference time: system prompts, retrieved documents (RAG), tool schemas, conversation history, and memory — optimized for **relevance over volume**. Research shows context quality matters more than prompt phrasing. Key concepts: the "lost in the middle" attention curve, lazy context loading, and token budget auditing.

=== "Advanced"

    Multi-component context pipeline optimization across 8 injection points (system prompt, history, RAG, tools, few-shot, memory, metadata, user message). Grounded in Liu et al.'s U-shaped attention curve (2023), Shopify's JIT instruction architecture for 50+ tools, and the 2026 empirical study (n=9,649) demonstrating context quality > prompt phrasing for frontier models. Practical engineering: token tax auditing, conditional vs. always-on context, compaction strategies, and retrieval reranking.

---

Context engineering is the discipline of designing, building, and optimizing the **complete information environment** an LLM operates within at inference time. It goes beyond prompt engineering — which focuses on the user-facing input — to encompass the entire data pipeline: system prompts, conversation history, retrieved documents, tool descriptions, few-shot examples, memory stores, and metadata.

> "The delicate art and science of filling the context window with just the right information for the next step." — Andrej Karpathy (2025)

---

## Why context engineering matters

Over 40% of AI project failures stem from poor or irrelevant context, not flawed models. A February 2026 peer-reviewed study across 9,649 experiments confirmed that **context quality matters more than prompt phrasing** for frontier models. Structured context reduces hallucination rates by 40%+ (Anthropic research).

The shift from "prompt engineering" to "context engineering" reflects a fundamental realization: the prompt is just one of eight or more components the model sees. Optimizing only the user message while ignoring system instructions, retrieved documents, tool schemas, and conversation history leaves most of the performance surface untouched.

---

## The eight components of a context window

| Component | What it is | Engineering lever |
|-----------|-----------|-------------------|
| **System prompt** | Identity, role, constraints, reasoning behavior | Compression, modularity, token budgeting |
| **Conversation history** | Prior turns in the current session | Trimming, summarization, compaction |
| **Retrieved documents (RAG)** | Chunks pulled from external knowledge stores | Retrieval quality, chunking strategy, reranking |
| **Tool descriptions** | Schemas and instructions for available tools | Just-in-time loading, tool filtering |
| **Few-shot examples** | Input-output pairs that demonstrate desired behavior | Example selection, dynamic few-shot |
| **Memory** | Facts persisted across sessions | Memory architecture (short-term, long-term, episodic) |
| **Metadata** | Timestamps, user info, session state | Selective injection, relevance filtering |
| **User message** | The actual prompt | Clarity, structure, specificity |

---

## Core principles

### Precision beats volume
The goal isn't more information — it's the **right** information. Selectively loading the most relevant 10–30% of available data improves accuracy and reduces cost. Shopify's Sidekick platform demonstrated this with "Just-in-Time (JIT) instructions" that deliver relevant context exactly when needed rather than overloading the system prompt.

### Lost in the middle
LLMs pay disproportionate attention to information at the **beginning and end** of the context window. The seminal "Lost in the Middle" paper (Liu et al., 2023) documented a U-shaped attention curve — critical details buried in the middle of a large context dump are frequently missed. Design documents and prompts to place important information at the boundaries.

### Effective vs. advertised context
Models advertise context windows of 128K, 200K, or 1M+ tokens, but empirical research consistently shows **degradation well before** the published cap. The "Maximum Effective Context Window" study demonstrated a significant gap between advertised and usable context length. Treat advertised limits as theoretical maxima, not operating targets.

### Lazy context loading
Load only data actively needed for the current step, not everything upfront. This mirrors software engineering's lazy initialization pattern. Agent frameworks like LangChain/LangGraph, Cursor's rules system (agent-decides vs. always-on), and Shopify's JIT architecture all implement this principle.

### Audit token costs
Every always-on instruction consumes tokens on every request. A 100-line system instruction costs 500–1,000 tokens per interaction. Context engineering includes regular audits: which instructions are always-on, which should be conditional, and which can be compressed without losing meaning.

---

## Key research and sources

| # | Source | Year | Why it matters |
|---|--------|------|---------------|
| 1 | [Liu et al., *Lost in the Middle* (arXiv:2307.03172)](https://arxiv.org/abs/2307.03172) | 2023 | Seminal paper on U-shaped attention — evidence at start/end of context is weighted more heavily than middle |
| 2 | [Lewis et al., *Retrieval-Augmented Generation* (arXiv:2005.11401)](https://arxiv.org/abs/2005.11401) | 2020 | Foundational RAG paper — retrieve what matters instead of stuffing the window |
| 3 | [Anthropic — Context windows](https://docs.anthropic.com/en/docs/build-with-claude/context-windows) | 2025 | Official definition: context = working memory; covers linear growth, context rot, compaction |
| 4 | [Anthropic — Compaction](https://docs.anthropic.com/en/docs/build-with-claude/compaction) | 2025 | How long-running threads get summarized when approaching limits |
| 5 | [Anthropic — Prompt engineering / Claude best practices](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/claude-4-best-practices) | 2025 | Structure, clarity, and agentic prompt patterns |
| 6 | [OpenAI — Conversation state](https://platform.openai.com/docs/guides/conversation-state) | 2025 | Stateful threads, context window billing, chaining responses |
| 7 | [Shopify Engineering — Building production-ready agentic systems](https://shopify.engineering/building-production-ready-agentic-systems) | 2025 | JIT instructions in production: deliver relevant tool data exactly when needed across 50+ tools |
| 8 | [Andrej Karpathy — Context engineering framing](https://the-decoder.com/shopify-ceo-and-ex-openai-researcher-agree-that-context-engineering-beats-prompt-engineering) | 2025 | Karpathy and Shopify CEO Tobi Lutke on why context engineering supersedes prompt engineering |
| 9 | [*Maximum Effective Context Window* (OAJAIML, 2024)](https://www.oajaiml.com/archive/context-is-what-you-need-the-maximum-effective-context-window-for-real-world-limits-of-llms) | 2024 | Empirical gap between advertised and usable context; degradation curves |
| 10 | [Simon Willison — Long context and context engineering](https://simonwillison.net/tags/long-context/) | Ongoing | Practitioner notes on model + tool ecosystem; long context is powerful but still requires engineering |
| 11 | [*Context Engineering vs Prompt Engineering* (KeepMyPrompts, 2026)](https://www.keepmyprompts.com/blog/en/context-engineering-vs-prompt-engineering-2026) | 2026 | Data from 9,649 experiments: context quality > prompt phrasing for frontier models |
| 12 | [Cursor — Rules (official)](https://cursor.com/docs/context/rules) | 2025 | Models don't retain memory between completions; rules = persistent prompt-level context — context engineering in practice |

---

## Practical takeaways

1. **Treat the system prompt as a product.** Version it, measure its token cost, and compress ruthlessly. Shopify reduced their agent system prompt while improving all metrics by moving to JIT context.
2. **Retrieval quality > retrieval volume.** A well-ranked top-5 chunk set outperforms a dump of 50 loosely relevant chunks. Invest in chunking, embedding quality, and reranking.
3. **Design for the U-curve.** Put your most critical instructions at the start of the system prompt and the most critical user context at the end. Avoid burying key facts in the middle of long documents.
4. **Compact proactively.** Don't wait for the context window to fill and the model to degrade. Implement summarization and compaction strategies before you hit limits.
5. **Make context conditional.** Use patterns like Cursor's agent-decides rules or Shopify's JIT loading to inject context only when relevant. Always-on context is expensive and often irrelevant.

---

## Further reading

- **Quick reading list (26 links):** [`cursor-knowledge/ai-context-reading-list.md`](../cursor-knowledge/ai-context-reading-list.md) — companion to the onboarding guides; covers context windows, memory, RAG, and IDE agent practices
- **Full bibliography:** [SOURCE_INDEX.md](SOURCE_INDEX.md)
