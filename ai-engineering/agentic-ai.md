# Agentic AI

## At a glance

=== "Beginner"

    An AI agent is an AI assistant that can **do things**, not just talk. Instead of one question and one answer, an agent can search the web, run code, read files, and take multiple steps to complete a task — like a helpful colleague who can actually carry out the work, not just suggest it. Cursor's Agent mode is an example of this in action.

=== "Intermediate"

    AI agents use LLMs in a **think-act-observe loop**: the model reasons about the current state, calls a tool (search, code execution, API), reads the result, and iterates. Key patterns include ReAct (interleaved reasoning and acting), tool use / function calling, and multi-agent orchestration. Memory systems (short-term context + long-term stores) and planning strategies (CoT, Tree of Thoughts, DAG decomposition) extend what a single prompt can accomplish.

=== "Advanced"

    Agent = LLM + memory + planning + tool use (Weng, 2023). Foundational patterns: ReAct (Yao et al., 2022), Toolformer (Schick et al., 2023), and planner-centric DAG frameworks (2025). Memory taxonomy: short-term (context window), long-term (vector stores), episodic (action logs). Multi-agent: orchestrator-specialist, debate/verification, swarm handoff (AutoGen, CrewAI, LangGraph). Reliability frontier: PROBE benchmark shows ~40% end-to-end SOTA; compounding error rate = (per-step accuracy)^n.

---

An **AI agent** is a system where an LLM drives a loop of **reasoning, acting, and observing** — deciding which tools to call, interpreting results, and iterating until a goal is met. Unlike a single prompt-response exchange, agents maintain state across multiple steps, use external tools, and can plan multi-step workflows autonomously.

> Agent = LLM + memory + planning + tool use — Lilian Weng (2023)

---

## Why agents matter

Single-turn LLM interactions hit a ceiling quickly. Real-world tasks — "research this topic and write a report," "debug this application," "find flights and book the cheapest one" — require **sequential decision-making**: gather information, reason about it, take action, observe the result, adjust. Agents bridge the gap between "smart autocomplete" and "autonomous collaborator."

The agent paradigm also makes LLMs **extensible** — they can search the web, query databases, execute code, call APIs, and interact with software. The model's knowledge is no longer limited to its training data.

---

## Core architecture patterns

### ReAct (Reasoning + Acting)
The foundational agent pattern. The model alternates between **Thought** (reasoning about the current state), **Action** (calling a tool), and **Observation** (reading the tool's output). This interleaving allows the model to course-correct based on real feedback rather than hallucinating multi-step plans. Introduced by Yao et al. (2022).

### Tool use / function calling
Models are trained or prompted to output structured tool calls (JSON function calls, API requests, code execution). The orchestration layer executes the call and feeds the result back. OpenAI's function calling, Anthropic's tool use, and Google's function calling all implement this pattern with slightly different schemas.

### Planning and decomposition
Complex tasks require the agent to **break a goal into subtasks** before executing. Techniques include:
- **Chain of Thought (CoT)** — step-by-step reasoning within a single turn
- **Tree of Thoughts (ToT)** — exploring multiple reasoning branches and selecting the best
- **DAG planning** — decomposing into a directed acyclic graph of dependent subtasks (the "Beyond ReAct" approach)

### Memory systems
Agents need memory beyond the current context window:
- **Short-term memory** — the conversation history and current context; managed by trimming and compaction
- **Long-term memory** — facts persisted across sessions in vector stores, databases, or files
- **Episodic memory** — records of past actions and their outcomes, enabling the agent to learn from experience

### Multi-agent systems
Instead of one monolithic agent, split tasks across **specialized agents** that communicate:
- **Orchestrator + specialists** — a coordinator routes tasks to domain-specific agents (coding, research, analysis)
- **Debate / verification** — agents check each other's work to reduce hallucination
- **Swarm patterns** — lightweight agents that hand off to each other based on context

Frameworks like AutoGen (Microsoft), CrewAI, and LangGraph implement multi-agent orchestration patterns.

---

## The reliability problem

Agents are powerful but fragile. Key failure modes:

| Failure mode | What happens | Mitigation |
|-------------|-------------|------------|
| **Compounding errors** | Early mistakes propagate through the action chain | Self-verification steps; human checkpoints |
| **Tool misuse** | Agent calls wrong tool or passes bad arguments | Constrained tool schemas; retry with error feedback |
| **Infinite loops** | Agent repeats the same action without progress | Step limits; loop detection; escalation to human |
| **Hallucinated plans** | Agent confidently outlines a plan it can't execute | Ground plans in available tools; validate before acting |
| **Context window exhaustion** | Long agent runs fill the context with tool outputs | Summarization; selective history; memory offloading |

The PROBE benchmark (2025) found that even state-of-the-art models achieve only ~40% end-to-end performance on proactive problem-solving tasks, highlighting how far the field has to go.

---

## Key research and sources

| # | Source | Year | Why it matters |
|---|--------|------|---------------|
| 1 | [Yao et al., *ReAct: Synergizing Reasoning and Acting* (arXiv:2210.03629)](https://arxiv.org/abs/2210.03629) | 2022 | Foundational agent pattern — interleave thought, action, and observation to ground reasoning in real feedback |
| 2 | [Schick et al., *Toolformer* (arXiv:2302.04761)](https://arxiv.org/abs/2302.04761) | 2023 | Self-taught tool use — LLM learns when and how to call tools without explicit instruction |
| 3 | [Lilian Weng, *LLM Powered Autonomous Agents* (Lil'Log)](https://lilianweng.github.io/posts/2023-06-23-agent/) | 2023 | Definitive overview: Agent = LLM + memory + planning + tool use; case studies of AutoGPT, ChemCrow, generative agents |
| 4 | [*A Survey on the Memory Mechanism of LLM-based Agents* (arXiv:2404.13501)](https://arxiv.org/abs/2404.13501) | 2024 | Taxonomy of short-term vs long-term agent memory; design patterns for memory architectures |
| 5 | [*The Landscape of Agentic RL for LLMs: A Survey* (TMLR, 2026)](https://arxiv.org/abs/2509.02547) | 2026 | 500+ works synthesized; distinguishes agentic RL from standard RLHF; taxonomy of planning, tool use, memory, reasoning |
| 6 | [*Beyond ReAct: Planner-Centric Framework* (arXiv:2511.10037)](https://arxiv.org/abs/2511.10037) | 2025 | DAG planning for complex multi-tool workflows; addresses ReAct's local optimization limitations |
| 7 | [Anthropic — Tool use documentation](https://docs.anthropic.com/en/docs/build-with-claude/tool-use) | 2025 | Official guide to Claude's function calling and tool integration patterns |
| 8 | [LangChain / LangGraph documentation](https://python.langchain.com/docs/introduction/) | Ongoing | Most widely adopted agent framework; covers chains, agents, tool integration, and multi-agent graphs |
| 9 | [Microsoft AutoGen documentation](https://microsoft.github.io/autogen/) | 2024 | Multi-agent conversation framework; specialized agents communicate to solve tasks collaboratively |
| 10 | [CrewAI documentation](https://docs.crewai.com/) | 2024 | Role-based multi-agent orchestration; agents with defined roles, goals, and backstories |
| 11 | [*PROBE: Measuring Proactive Problem Solving in LLM Agents* (2025)](https://openreview.net/forum?id=probe-benchmark-2025) | 2025 | Benchmarks proactive agent behavior; decomposes into searching, identifying, and executing — SOTA achieves ~40% |
| 12 | [Cognition AI — Devin (technical overview)](https://www.cognition.ai/blog/introducing-devin) | 2024 | First autonomous software engineer agent; demonstrates long-horizon coding tasks with planning, debugging, and deployment |

---

## Practical takeaways

1. **Start with ReAct, not multi-agent.** The simplest agent pattern — think, act, observe — solves most use cases. Multi-agent systems add coordination overhead that's only justified for genuinely parallel, specialized workflows.
2. **Tools are the agent's hands.** The quality of your tool descriptions and schemas matters as much as the model's reasoning ability. Bad tool docs → bad tool calls → failed agents.
3. **Build in guardrails from day one.** Step limits, human-in-the-loop checkpoints, and structured output validation prevent the compounding error problem that makes agents unreliable.
4. **Memory is the hardest unsolved problem.** Short-term context management is tractable. Long-term memory that actually helps the agent make better decisions across sessions is still an active research frontier.
5. **Measure end-to-end, not per-step.** An agent that gets each step 90% right still fails ~65% of the time over 10 steps (0.9^10 ≈ 0.35). Reliability at the task level is what matters.

---

## Further reading

- **Context engineering (what agents see):** [context-engineering.md](context-engineering.md)
- **Full-stack LLM (deploying agent systems):** [full-stack-llm.md](full-stack-llm.md)
- **Full bibliography:** [SOURCE_INDEX.md](SOURCE_INDEX.md)
