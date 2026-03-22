# LLM foundations

## At a glance

=== "Beginner"

    Large language models (LLMs) like ChatGPT and Claude are AI systems that learned to write by reading enormous amounts of text. They predict "what word comes next" — and that simple trick, at massive scale, produces systems that can write, reason, translate, and code. You don't need to understand the math to use them, but knowing the basics helps you understand **why** they sometimes get things wrong.

=== "Intermediate"

    LLMs are transformer-based neural networks trained on trillions of tokens via next-token prediction. After pre-training (general language understanding), they're fine-tuned with instruction data (SFT) and aligned with human preferences (RLHF or DPO). Scaling laws predict that performance improves predictably with model size, data, and compute — but the "Chinchilla" finding showed most models were undertrained on data relative to their size.

=== "Advanced"

    Decoder-only transformer architecture (Vaswani et al., 2017) with multi-head self-attention, positional encoding, and feed-forward layers. Pre-training on causal language modeling; post-training via SFT, PPO-based RLHF (Ouyang et al., 2022), DPO (Rafailov et al., 2023), or pure RL (DeepSeek-R1 GRPO). Scaling governed by Kaplan (2020) and Chinchilla-optimal (Hoffmann, 2022) laws; data wall approaching 2026–2028. Post-training scaling (ACL 2025 survey) emerging as the next frontier.

---

Large language models (LLMs) are neural networks trained on massive text corpora to predict the next token in a sequence. That simple objective — next-token prediction — produces systems that can write code, reason about problems, translate languages, and hold conversations. This article covers the foundational research: the transformer architecture, how models are trained, what scaling laws predict, and the key papers that define the field.

---

## The transformer architecture

The **transformer** (Vaswani et al., 2017) replaced recurrent neural networks (RNNs) as the dominant architecture for language modeling. Its core innovation is **self-attention**: instead of processing tokens sequentially, the transformer computes relationships between all tokens in parallel, allowing it to capture long-range dependencies efficiently.

Key components:
- **Multi-head self-attention** — each head learns different relationship patterns (syntax, semantics, co-reference)
- **Positional encoding** — since attention is order-agnostic, explicit position signals tell the model where each token sits
- **Feed-forward layers** — per-position nonlinear transformations that store factual knowledge
- **Layer normalization and residual connections** — stabilize training at scale

The original transformer was an encoder-decoder model for translation. Modern LLMs typically use **decoder-only** architectures (GPT lineage) — they generate text autoregressively, one token at a time, conditioned on all preceding tokens.

---

## Training paradigms

### Pre-training
The model learns general language understanding from massive corpora (trillions of tokens from the web, books, code, and structured data). The objective is typically **causal language modeling** — predict the next token given all previous tokens. Pre-training is the most expensive phase, costing millions of dollars for frontier models.

### Supervised fine-tuning (SFT)
After pre-training, models are fine-tuned on curated datasets of instruction-response pairs to follow human instructions. This shifts the model from "predict the next likely internet token" to "produce a helpful, structured response to a user query."

### Reinforcement learning from human feedback (RLHF)
Human evaluators rank model outputs. A reward model is trained on these preferences, then used to optimize the language model via reinforcement learning (typically Proximal Policy Optimization / PPO). RLHF is what makes models like ChatGPT *feel* helpful and safe, not just capable.

### Direct Preference Optimization (DPO)
A simpler alternative to RLHF that skips the separate reward model. Instead, the language model is directly optimized on preference pairs — "response A is better than response B" — using a modified loss function. Increasingly popular for its stability and lower infrastructure requirements.

---

## Scaling laws

Scaling laws describe predictable relationships between **model size** (parameters), **training data** (tokens), and **compute** (FLOPs) on one hand, and model performance (measured as loss) on the other. Two landmark results:

**Kaplan et al. (2020):** Established that loss decreases as a power law with model size, dataset size, and compute. Larger models are more sample-efficient — they extract more from each training token. This paper drove the "bigger is better" era.

**Hoffmann et al. (2022, "Chinchilla"):** Showed that Kaplan's scaling was compute-suboptimal. For a fixed compute budget, you should train a **smaller model on more data** than the field was doing. Chinchilla (70B parameters, 1.4T tokens) matched the performance of Gopher (280B parameters, 300B tokens) at lower cost. This rebalanced the field toward data efficiency.

**Current state (2025–2026):** The scaling laws survey (arXiv:2502.18969) analyzes 50+ papers and identifies critical unresolved questions — discrepancies in optimal token-to-parameter ratios, underreported methodological details, and the approaching "data wall" as high-quality internet text is exhausted (projected 2026–2028). Post-training scaling (SFT, RLHF, test-time compute) is emerging as the next performance frontier.

---

## Key models and their contributions

| Model | Org | Year | Contribution |
|-------|-----|------|-------------|
| **GPT-3** | OpenAI | 2020 | Demonstrated that scale alone produces emergent capabilities (in-context learning, few-shot) |
| **Chinchilla** | DeepMind | 2022 | Proved compute-optimal training requires more data, not just more parameters |
| **GPT-4** | OpenAI | 2023 | Multimodal (text + vision); demonstrated reasoning capabilities at a new level; technical report withheld architecture details |
| **Llama 2/3** | Meta | 2023–24 | Open-weight models that democratized LLM research; Llama 3 at 405B rivals proprietary models |
| **Claude 3/4** | Anthropic | 2024–25 | Constitutional AI approach; long context windows (200K+); strong reasoning and safety properties |
| **DeepSeek-R1** | DeepSeek | 2025 | Pure RL training (no SFT) achieved 79.8% on MATH; demonstrated that reasoning can emerge from RL alone |
| **Gemini** | Google | 2024–25 | Natively multimodal (text, image, audio, video); long context (1M+ tokens); integrated with Google ecosystem |

---

## Key research and sources

| # | Source | Year | Why it matters |
|---|--------|------|---------------|
| 1 | [Vaswani et al., *Attention Is All You Need* (arXiv:1706.03762)](https://arxiv.org/abs/1706.03762) | 2017 | The transformer paper — self-attention replaces recurrence; foundation of every modern LLM |
| 2 | [Kaplan et al., *Scaling Laws for Neural Language Models* (arXiv:2001.08361)](https://arxiv.org/abs/2001.08361) | 2020 | Power-law relationships between scale and performance; drove the "bigger is better" paradigm |
| 3 | [Hoffmann et al., *Training Compute-Optimal LLMs* (arXiv:2203.15556)](https://arxiv.org/abs/2203.15556) | 2022 | Chinchilla scaling — smaller model + more data beats bigger model + less data at fixed compute |
| 4 | [OpenAI, *GPT-4 Technical Report* (arXiv:2303.08774)](https://arxiv.org/abs/2303.08774) | 2023 | Multimodal frontier model; benchmark results across professional exams; limited architecture disclosure |
| 5 | [Meta, *Llama 3 Herd of Models* (arXiv:2407.21783)](https://arxiv.org/abs/2407.21783) | 2024 | Open-weight models up to 405B; detailed training methodology; multimodal and multilingual |
| 6 | [DeepSeek, *DeepSeek-R1 Technical Report*](https://arxiv.org/abs/2501.12948) | 2025 | Pure RL training produces strong reasoning without SFT; open-source; challenges proprietary models |
| 7 | [Zhao et al., *A Survey of Large Language Models* (arXiv:2303.18223)](https://arxiv.org/abs/2303.18223) | 2023 (updated 2025) | Comprehensive survey: pre-training, adaptation, utilization, and emergent abilities — regularly updated |
| 8 | [*(Mis)Fitting: A Survey of Scaling Laws* (arXiv:2502.18969)](https://arxiv.org/abs/2502.18969) | 2025 | Analyzes 50+ papers on scaling; identifies discrepancies and open questions in the field |
| 9 | [Jay Alammar, *The Illustrated Transformer*](https://jalammar.github.io/illustrated-transformer/) | 2018 | The best visual explanation of transformer internals — widely cited as the go-to learning resource |
| 10 | [Andrej Karpathy, *Let's build GPT from scratch*](https://www.youtube.com/watch?v=kCc8FmEb1nY) | 2023 | Builds a GPT from scratch in code; paired with [nanoGPT](https://github.com/karpathy/nanoGPT) for hands-on learning |
| 11 | [Lilian Weng, *Large Language Model overview* (Lil'Log)](https://lilianweng.github.io/posts/2023-01-27-the-transformer-family/) | 2023 | Comprehensive technical walkthrough of transformer variants and training techniques |
| 12 | [Post-Training Scaling survey (ACL 2025)](https://aclanthology.org/2025.acl-long.140/) | 2025 | Categorizes SFT, RLxF, and test-time compute as the next scaling frontier after pre-training plateaus |

---

## Practical takeaways

1. **Understand what you're paying for.** Pre-training creates general capability; fine-tuning and RLHF shape behavior. When a model "fails," diagnose which layer is the bottleneck — capability (pre-training), instruction following (SFT), or alignment (RLHF/DPO).
2. **Scaling laws inform build-vs-buy.** If Chinchilla-optimal training of a 70B model requires 1.4T tokens and months of GPU time, most teams should use existing foundation models and invest in fine-tuning and context engineering instead.
3. **Open-weight models are viable.** Llama 3, DeepSeek, Mistral, and others offer competitive performance with full weight access. This matters for latency-sensitive deployment, privacy requirements, and cost control.
4. **The data wall is real.** High-quality training data is finite. The field is shifting toward synthetic data, post-training scaling, and test-time compute. Understanding this trend helps evaluate which model capabilities will improve next.

---

## Further reading

- **Full bibliography:** [SOURCE_INDEX.md](SOURCE_INDEX.md)
- **Context engineering (what the model sees):** [context-engineering.md](context-engineering.md)
- **Putting models into production:** [full-stack-llm.md](full-stack-llm.md)
