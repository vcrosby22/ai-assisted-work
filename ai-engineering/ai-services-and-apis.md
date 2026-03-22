# AI services and APIs

## At a glance

=== "Beginner"

    When you use Cursor, ChatGPT, or Claude, you're using an AI **service** — someone else runs the model and you access it through the internet. There are several providers to choose from (Anthropic, OpenAI, Google, and others), some free, some paid. You can also run smaller AI models on your own computer. This article explains the options and what to watch out for.

=== "Intermediate"

    The provider landscape: proprietary APIs (Anthropic Claude, OpenAI GPT-4, Google Gemini), cloud wrappers (AWS Bedrock, Azure OpenAI, Vertex AI), and open-weight models (Llama, Mistral) via Hugging Face or self-hosted with vLLM/Ollama. Choice depends on quality needs, latency budget, privacy requirements, and cost. Multi-model architectures (cheap model for routing, capable model for reasoning) are becoming standard. OWASP Top 10 for LLM apps covers the security layer.

=== "Advanced"

    Provider selection matrix across reasoning quality, latency, cost, data residency, and compliance (SOC 2, HIPAA, EU AI Act). Multi-model routing: classifier → fast model (Haiku/Flash) for simple tasks, capable model (Opus/o3) for complex reasoning. Open-weight frontier: Llama 3 405B and DeepSeek-R1 approach proprietary quality with full weight access. Security: OWASP LLM Top 10 (prompt injection, excessive agency), NIST AI RMF (Govern/Map/Measure/Manage), EU AI Act risk classification.

---

This article maps the **commercial and open-source landscape** for accessing LLMs — the APIs, platforms, and model hubs a practitioner chooses between when building AI-powered applications. It also covers **security** and **governance** frameworks that apply regardless of which provider you choose.

---

## The provider landscape

### Proprietary API providers

| Provider | Flagship models | Key differentiator | Documentation |
|----------|---------------|-------------------|---------------|
| **Anthropic** | Claude 4 (Opus, Sonnet), Claude 3.5 | Constitutional AI; strong reasoning and safety; 200K+ context; tool use | [docs.anthropic.com](https://docs.anthropic.com/) |
| **OpenAI** | GPT-4o, GPT-4 Turbo, o1/o3 reasoning | Largest ecosystem; function calling; assistants API; multimodal | [platform.openai.com](https://platform.openai.com/docs/) |
| **Google** | Gemini 2.0 (Pro, Flash, Ultra) | Natively multimodal (text, image, audio, video); 1M+ context; integrated with Google Cloud | [ai.google.dev](https://ai.google.dev/docs) |

### Cloud platform wrappers

| Platform | What it offers | When to use it |
|----------|---------------|----------------|
| **AWS Bedrock** | Managed access to Anthropic, Meta, Mistral, Cohere, and Amazon models through a unified API | You're already on AWS; need enterprise compliance; want model choice without multiple vendor contracts |
| **Azure OpenAI Service** | OpenAI models (GPT-4, DALL-E, Whisper) hosted on Azure with enterprise security and compliance | You're on Azure; need data residency guarantees; enterprise procurement |
| **Google Vertex AI** | Gemini models + open models (Llama, Mistral) + fine-tuning + MLOps | You're on GCP; need end-to-end ML pipeline; want Gemini natively |

### Open-weight models and hubs

| Resource | What it offers | Key models |
|----------|---------------|------------|
| **Hugging Face Hub** | Model hosting, inference API, Spaces (demo apps), training libraries | Llama 3, Mistral, Gemma, Phi, thousands of fine-tuned variants |
| **Meta Llama** | Open-weight models with permissive license (up to 405B) | Llama 3.1 (8B, 70B, 405B); multimodal and multilingual |
| **Mistral AI** | European open-weight models; strong code and multilingual performance | Mistral Large, Mixtral (mixture of experts), Codestral |
| **Ollama** | One-command local model running; developer-friendly CLI | Runs any GGUF-quantized model locally; great for prototyping |

---

## Choosing a provider

There is no single best provider. The decision depends on your constraints:

| Constraint | Lean toward |
|-----------|-------------|
| **Maximum reasoning quality** | Anthropic Claude 4 Opus or OpenAI o3 |
| **Lowest latency** | Smaller models (Gemini Flash, Claude Haiku, GPT-4o mini) or self-hosted quantized models |
| **Lowest cost** | Open-weight models self-hosted; or Gemini Flash / Claude Haiku for API |
| **Data privacy / on-premises** | Open-weight models (Llama, Mistral) self-hosted via vLLM or TGI |
| **Multimodal (vision, audio, video)** | Gemini 2.0 (natively multimodal) or GPT-4o |
| **Enterprise compliance** | AWS Bedrock or Azure OpenAI (SOC 2, HIPAA, data residency) |
| **Rapid prototyping** | OpenAI API (largest ecosystem, most examples) or Ollama (local, free) |

### The multi-model strategy
Most production systems use **multiple models**: a fast, cheap model for classification and routing; a capable model for complex reasoning; a specialized model for code generation. Design your architecture to swap models without rewriting business logic.

---

## Security and governance

Regardless of provider, LLM applications face security and governance challenges that don't exist in traditional software:

### OWASP Top 10 for LLM Applications
The OWASP Foundation maintains a specific top-10 vulnerability list for LLM applications. Key risks include:
- **Prompt injection** — malicious input overrides system instructions
- **Insecure output handling** — LLM output used directly in SQL, HTML, or system commands
- **Training data poisoning** — adversarial data corrupts model behavior
- **Sensitive information disclosure** — model reveals training data or system prompts
- **Excessive agency** — agent given too many permissions without human oversight

### NIST AI Risk Management Framework
NIST's AI RMF provides a structured approach to AI risk management across four functions: **Govern** (policies and accountability), **Map** (contextualize risks), **Measure** (assess and track), **Manage** (mitigate and monitor). Useful for organizations that need defensible AI governance.

### EU AI Act
The EU AI Act (effective 2025–2026) classifies AI systems by risk level — **unacceptable**, **high**, **limited**, **minimal** — with compliance requirements scaling accordingly. Foundation model providers ("general-purpose AI") have specific transparency and documentation obligations.

---

## Key sources

| # | Source | Year | Why it matters |
|---|--------|------|---------------|
| 1 | [Anthropic API documentation](https://docs.anthropic.com/) | Ongoing | Claude models, tool use, prompt engineering, safety — the provider this repo's maintainer uses most |
| 2 | [OpenAI Platform documentation](https://platform.openai.com/docs/) | Ongoing | GPT-4, function calling, assistants, embeddings — largest API ecosystem |
| 3 | [Google AI / Gemini documentation](https://ai.google.dev/docs) | Ongoing | Natively multimodal models; long context; Vertex AI integration |
| 4 | [AWS Bedrock documentation](https://docs.aws.amazon.com/bedrock/) | Ongoing | Multi-model managed service; enterprise compliance |
| 5 | [Azure OpenAI Service documentation](https://learn.microsoft.com/en-us/azure/ai-services/openai/) | Ongoing | OpenAI models on Azure with enterprise security |
| 6 | [Hugging Face Hub and Inference API](https://huggingface.co/docs) | Ongoing | Open model ecosystem; inference, fine-tuning, evaluation tooling |
| 7 | [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/) | 2025 | The standard security vulnerability list for LLM apps — prompt injection, data poisoning, excessive agency |
| 8 | [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) | 2023 | Structured AI risk management: Govern, Map, Measure, Manage — widely adopted in enterprise |

---

## Practical takeaways

1. **Start with an API, not self-hosting.** Unless you have specific privacy, latency, or cost requirements that mandate self-hosting, proprietary APIs are faster to ship and easier to maintain.
2. **Abstract the provider.** Use a thin wrapper or framework (LangChain, LiteLLM, your own adapter) so you can swap models without rewriting application code. Provider lock-in is real and expensive.
3. **Budget for the security layer.** Prompt injection is not a theoretical risk — it's a practical one. Input validation, output sanitization, and permission scoping are baseline requirements.
4. **Track the open-weight frontier.** Llama 3 405B and DeepSeek-R1 are competitive with proprietary models for many tasks. The gap is closing; self-hosting economics improve continuously.
5. **Compliance is not optional.** If you're in a regulated industry or serving EU users, the AI Act and NIST RMF are not "nice to have" — they're requirements. Factor governance into your architecture, not as an afterthought.

---

## Further reading

- **Full-stack LLM (deploying what you choose):** [full-stack-llm.md](full-stack-llm.md)
- **Context engineering (maximizing model performance):** [context-engineering.md](context-engineering.md)
- **Full bibliography:** [SOURCE_INDEX.md](SOURCE_INDEX.md)
