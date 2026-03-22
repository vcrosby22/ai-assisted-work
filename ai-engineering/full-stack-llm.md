# Full-stack LLM development

## At a glance

=== "Beginner"

    Building an AI product involves more than just chatting with a model. You need to **choose a model**, **teach it your domain** (fine-tuning), **make it fast enough** for real users (inference), **measure if it works** (evaluation), and **keep it running** (deployment). This article covers the engineering decisions between "I have access to an AI" and "I have a product people can use."

=== "Intermediate"

    The full LLM stack: parameter-efficient fine-tuning (LoRA, QLoRA), alignment via RLHF or DPO, inference serving (vLLM, TGI), quantization for cost/speed tradeoffs, evaluation (benchmarks, LLM-as-judge, Chatbot Arena), and production operations (observability, prompt versioning, cost tracking). Key decision: start with prompting + RAG before fine-tuning; fine-tune only when you've exhausted cheaper approaches.

=== "Advanced"

    LoRA (Hu et al., 2021): rank-decomposed weight updates at <1% parameter cost. QLoRA (Dettmers, 2023): 4-bit NF4 quantization + LoRA for 65B models on consumer GPUs. Alignment: PPO-RLHF (Ouyang, 2022), DPO (Rafailov, 2023), GRPO (DeepSeek). Inference: PagedAttention (vLLM), INT4/AWQ/GPTQ quantization, KV-cache optimization. Evaluation: LMSYS Elo, LLM-as-judge calibration, faithfulness metrics. Production gap (Huyen): non-determinism, output format fragility, silent failures.

---

Building a production LLM application means more than calling an API. The "full stack" spans **fine-tuning** (adapting a model to your domain), **inference serving** (running the model at scale), **evaluation** (measuring whether it actually works), and **deployment** (keeping it running reliably). This article covers the engineering layer between "I have a foundation model" and "I have a product."

> "It's easy to make something cool with LLMs, but very hard to make something production-ready." — Chip Huyen (2023)

---

## Fine-tuning

### When to fine-tune vs. prompt
Fine-tuning trains the model's weights on your data. Prompting and context engineering modify the input without changing the model. The decision depends on:

| Factor | Use prompting / RAG | Fine-tune |
|--------|-------------------|-----------|
| **Data volume** | Small (dozens of examples) | Large (thousands+) |
| **Task specificity** | General instruction following | Domain-specific format, tone, or knowledge |
| **Latency budget** | Can tolerate longer prompts | Need shorter prompts + internalized behavior |
| **Update frequency** | Knowledge changes often | Behavior is stable, knowledge via RAG |
| **Cost structure** | Pay per token at inference | Pay upfront for training, cheaper inference |

### Parameter-efficient fine-tuning (PEFT)
Full fine-tuning updates all model parameters — expensive and requires substantial GPU memory. PEFT methods update a small fraction:

- **LoRA (Low-Rank Adaptation)** — injects small trainable matrices into attention layers; typically updates <1% of parameters while achieving 90%+ of full fine-tuning performance. The foundational paper by Hu et al. (2021).
- **QLoRA** — combines LoRA with 4-bit quantization, enabling fine-tuning of 65B+ parameter models on a single consumer GPU. Dettmers et al. (2023).

### RLHF and preference optimization
After SFT (supervised fine-tuning), alignment techniques shape model behavior:
- **RLHF** (Ouyang et al., 2022) — train a reward model on human preferences, then optimize the LLM via PPO. The technique behind ChatGPT's helpfulness.
- **DPO** (Rafailov et al., 2023) — directly optimize on preference pairs without a separate reward model. Simpler, more stable, increasingly preferred.
- **GRPO** (Group Relative Policy Optimization) — used by DeepSeek for reasoning; optimizes on groups of sampled responses without a learned reward model.

---

## Inference serving

Running LLMs in production requires specialized infrastructure:

### Key concerns
- **Latency** — time to first token (TTFT) and tokens per second. Users notice >2s TTFT.
- **Throughput** — requests per second across concurrent users.
- **Cost** — GPU-hours per request. Dominates production costs.
- **Memory** — large models may not fit in a single GPU's VRAM; require model parallelism or quantization.

### Inference engines
| Engine | Key feature |
|--------|------------|
| **vLLM** | PagedAttention for efficient KV-cache management; high throughput for batch serving |
| **TGI (Text Generation Inference)** | Hugging Face's production server; supports quantization, tensor parallelism, streaming |
| **TensorRT-LLM** | NVIDIA's optimized engine; INT4/INT8 quantization with hardware acceleration |
| **Ollama** | Local inference with one-command model downloads; developer-friendly for prototyping |

### Quantization
Reducing model precision (FP16 → INT8 → INT4) shrinks memory footprint and increases speed at the cost of some quality. AWQ, GPTQ, and GGUF are common quantization formats. For many applications, INT4 quantization delivers 90%+ of FP16 quality at 4x memory reduction.

---

## Evaluation

LLM evaluation is notoriously difficult — outputs are open-ended, subjective, and context-dependent.

### Evaluation approaches
| Approach | What it measures | Limitations |
|----------|-----------------|-------------|
| **Benchmarks** (MMLU, HumanEval, MATH) | Specific capability on standardized tasks | May not reflect real-world performance |
| **LLM-as-judge** | Automated quality assessment using another LLM | Biases (verbosity, position); requires calibration |
| **Human evaluation** | Ground truth on quality, safety, helpfulness | Expensive, slow, hard to scale |
| **A/B testing** | Real user preference in production | Requires production traffic; slow feedback loop |
| **LMSYS Chatbot Arena** | Crowdsourced blind comparisons between models | Public leaderboard; strong signal for relative model quality |

### What to measure
- **Accuracy / correctness** — does the output match ground truth?
- **Faithfulness** — does the output stay grounded in provided context (not hallucinate)?
- **Helpfulness** — does it actually answer the user's question?
- **Safety** — does it refuse harmful requests? Avoid generating problematic content?
- **Latency and cost** — fast enough and cheap enough for the use case?

---

## Deployment and operations

### Observability
LLM applications need purpose-built observability:
- **Trace logging** — capture full prompt, response, latency, token count, and model version for every request
- **Cost tracking** — token usage drives cost; track per-user, per-feature, per-model
- **Quality monitoring** — automated checks for hallucination, refusal rates, and output format compliance

### Experiment tracking
Tools like **Weights & Biases**, **MLflow**, and **LangSmith** track training runs, prompt versions, evaluation scores, and deployment metrics. Version your prompts and context configurations the same way you version code.

### The production gap
Chip Huyen's framework identifies key production challenges:
- **Non-determinism** — same input can produce different outputs; complicates testing
- **Output format fragility** — no guarantee the model returns valid JSON, Markdown, or whatever downstream systems expect
- **Natural language ambiguity** — instructions that seem clear to humans are ambiguous to models
- **Silent failures** — the model produces plausible-sounding wrong answers; no error code, no stack trace

---

## Key research and sources

| # | Source | Year | Why it matters |
|---|--------|------|---------------|
| 1 | [Chip Huyen, *Building LLM Applications for Production*](https://huyenchip.com/2023/04/11/llm-engineering.html) | 2023 | Definitive practitioner guide to production challenges: ambiguity, non-determinism, evaluation, cost |
| 2 | [Chip Huyen, *AI Engineering* (O'Reilly)](https://www.oreilly.com/library/view/ai-engineering/9781098166298/) | 2025 | Book-length treatment of building applications with foundation models |
| 3 | [Hu et al., *LoRA: Low-Rank Adaptation of Large Language Models* (arXiv:2106.09685)](https://arxiv.org/abs/2106.09685) | 2021 | Parameter-efficient fine-tuning — update <1% of parameters, get 90%+ of full fine-tuning quality |
| 4 | [Dettmers et al., *QLoRA* (arXiv:2305.14314)](https://arxiv.org/abs/2305.14314) | 2023 | Fine-tune 65B models on a single GPU via 4-bit quantization + LoRA |
| 5 | [Ouyang et al., *Training Language Models to Follow Instructions* (arXiv:2203.02155)](https://arxiv.org/abs/2203.02155) | 2022 | The InstructGPT / RLHF paper — the technique behind ChatGPT's helpfulness |
| 6 | [Rafailov et al., *Direct Preference Optimization* (arXiv:2305.18290)](https://arxiv.org/abs/2305.18290) | 2023 | Simpler alternative to RLHF; directly optimize on preference pairs without a reward model |
| 7 | [Post-Training Scaling survey (ACL 2025)](https://aclanthology.org/2025.acl-long.140/) | 2025 | SFT, RLxF, and test-time compute as the next scaling frontier |
| 8 | [vLLM — PagedAttention and efficient inference](https://docs.vllm.ai/) | 2023+ | High-throughput LLM serving with PagedAttention; the de facto open-source inference engine |
| 9 | [LMSYS Chatbot Arena](https://chat.lmsys.org/) | Ongoing | Crowdsourced model comparison via blind A/B testing; most trusted public LLM leaderboard |
| 10 | [Hugging Face — Transformers, PEFT, TRL ecosystem](https://huggingface.co/docs) | Ongoing | Open-source ecosystem for model hosting, fine-tuning (PEFT/TRL), inference, and evaluation |

---

## Practical takeaways

1. **Start with prompting and RAG before fine-tuning.** Fine-tuning is powerful but expensive and slow to iterate. Most applications should exhaust prompt engineering and retrieval-augmented generation first.
2. **Evaluation is the hardest part.** If you can't measure whether your application works, you can't improve it. Invest in evaluation infrastructure before scaling.
3. **LoRA is the 80/20 of fine-tuning.** For most domain adaptation tasks, LoRA on a strong base model outperforms full fine-tuning on cost and iteration speed.
4. **Instrument everything from day one.** Log prompts, responses, latency, token counts, and costs. You'll need this data for debugging, optimization, and cost control.
5. **Treat prompts as code.** Version them, test them, review them. A prompt change is a deployment.

---

## Further reading

- **LLM foundations (what you're fine-tuning):** [llm-foundations.md](llm-foundations.md)
- **AI services (which APIs to use):** [ai-services-and-apis.md](ai-services-and-apis.md)
- **Full bibliography:** [SOURCE_INDEX.md](SOURCE_INDEX.md)
