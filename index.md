# AI Assisted Work

Welcome to a **free, open collection** of guides, technical knowledge, and resources for learning [Cursor](https://www.cursor.com/) and AI-assisted work.

---

## Who is this for?

=== "Beginner"

    **You've never used Cursor or AI coding tools.** Maybe you're not a developer at all — you're a writer, PM, researcher, or someone curious about building things with AI. You want to try it without needing to learn programming first.

    *This knowledge base will walk you through installing Cursor, having your first AI conversation, and building your first project — in plain language, with no code required.*

=== "Intermediate"

    **You've used Cursor (or similar AI tools) and you're comfortable with the basics.** You can have a conversation with the assistant and get useful output, but you want to go deeper — managing context across sessions, using Git to save and share work, and customizing how the assistant behaves.

    *This knowledge base will help you level up your workflow, avoid common mistakes, and build more reliably.*

=== "Advanced"

    **You're an engineer, researcher, or technical power user.** You want to understand the systems behind AI assistants — LLM architectures, agent design patterns, context engineering, evaluation, and deployment. You read papers and want scholarly references, not just how-to guides.

    *This knowledge base includes a deep technical section with 54 annotated scholarly sources, plus 100+ total references across all topics.*

---

## Start here

=== "Beginner"

    1. [**Install Cursor & first steps**](onboarding/guides/installing-cursor-and-first-steps.md) — download, open a folder, first conversation *(10 min)*
    2. [**Building with agentic AI**](onboarding/guides/building-with-agentic-ai-non-technical.md) — the mindset: you steer, the AI builds
    3. [**First-week checklist**](onboarding/checklists/first-week-cursor-non-technical.md) — a light daily plan for days 1–7

    **No coding experience needed.** These guides assume zero programming background.

=== "Intermediate"

    - [**Working with AI context**](onboarding/guides/working-with-ai-context.md) — why the assistant forgets, and how to keep it accurate
    - [**Session playbook**](onboarding/guides/cursor-session-playbook.md) — terminal, GitHub, static sites, journaling
    - [**Git basics for non-developers**](onboarding/guides/git-basics-for-non-developers.md) — save versions, share on GitHub
    - [**Triggers & prompts**](onboarding/guides/cursor-triggers-and-prompts.md) — customize assistant behavior with rules and commands
    - [**Glossary**](product-management/GLOSSARY.md) — plain-language definitions for technical terms

=== "Advanced"

    - [**AI Engineering knowledge base**](ai-engineering/README.md) — LLM foundations, agentic AI, context engineering, full-stack LLM, AI services *(54 scholarly sources)*
    - [**Design & Web knowledge base**](design-knowledge/README.md) — UI, accessibility, e-commerce, REST APIs, agent load map
    - [**Context engineering deep dive**](ai-engineering/context-engineering.md) — the flagship article
    - [**Source index**](ai-engineering/SOURCE_INDEX.md) — master bibliography with annotated references
    - [**All sources**](sources.md) — 102 deduplicated references across the entire knowledge base

---

## Common questions

=== "Beginner"

    **Do I need to know how to code?**
    :   No. Many people use Cursor for writing, planning, and "no-code" style work. The beginner guides assume zero programming experience.

    **Is Cursor free?**
    :   Cursor has a free tier with limited AI usage. Paid plans unlock more. See [cursor.com/pricing](https://www.cursor.com/pricing).

    **What can I actually build?**
    :   Landing pages, documents, research summaries, structured plans, simple web apps, and more — by describing what you want in plain language.

    **What if I break something?**
    :   Cursor has undo. Git (version control) lets you go back to any saved point. The guides here teach both.

=== "Intermediate"

    **How do I keep the assistant accurate in long conversations?**
    :   Start a new chat when the topic shifts. Put important facts in files (not just chat) so the assistant can re-read them. See [Working with AI context](onboarding/guides/working-with-ai-context.md).

    **What's the difference between Plan and Agent mode?**
    :   **Plan** thinks with you and proposes changes for review. **Agent** edits files and runs commands directly. Use Plan when you want control, Agent when you trust the direction.

    **How do I share what I build?**
    :   Use Git to save versions and push to GitHub. From there you can share a repo link or publish a site with GitHub Pages. See [Git basics](onboarding/guides/git-basics-for-non-developers.md).

    **Can I customize how the assistant behaves?**
    :   Yes — rules files (`.cursor/rules/`), slash commands, and skills shape behavior per project. See [Triggers & prompts](onboarding/guides/cursor-triggers-and-prompts.md).

=== "Advanced"

    **What models does Cursor support?**
    :   Claude (Anthropic), GPT-4 (OpenAI), and others — selectable per conversation. Model availability depends on your plan tier.

    **What is context engineering?**
    :   Designing the information environment an LLM operates in — what it sees, when, and how. It directly affects output quality, hallucination rates, and agent reliability. See the [deep dive](ai-engineering/context-engineering.md).

    **Can I fine-tune models or bring my own API keys?**
    :   Cursor uses its own API layer — no custom endpoints today. For fine-tuning workflows outside the IDE, see [full-stack LLM](ai-engineering/full-stack-llm.md).

    **How do I evaluate agent reliability?**
    :   Track accuracy over time, compare model outputs, and build evaluation harnesses. The [AI engineering KB](ai-engineering/README.md) covers frameworks, and the [source index](ai-engineering/SOURCE_INDEX.md) links to key benchmarking papers.

---

## Explore the knowledge base

=== "Beginner"

    Everything you need to get started — no technical background required.

    | Section | What you'll find |
    |---------|-----------------|
    | [**Getting Started**](onboarding/guides/installing-cursor-and-first-steps.md) | Install Cursor, have your first AI conversation, follow a first-week plan |
    | [**Glossary**](product-management/GLOSSARY.md) | Plain-language definitions for every technical term you'll encounter |
    | [**Curated links**](onboarding/links/README.md) | Handpicked resources on AI safety, privacy, and research literacy |

=== "Intermediate"

    Deepen your practice — context management, version control, product frameworks.

    | Section | What you'll find |
    |---------|-----------------|
    | [**Guides & Reference**](onboarding/INDEX.md) | Git basics, triggers & prompts, slash commands, session playbooks |
    | [**Product Management**](product-management/README.md) | PM frameworks, backlog best practices, quality criteria |
    | [**Companion Articles**](cursor-knowledge/README.md) | AI context reading lists, mobile web UX, Git workflow patterns |
    | [**Glossary**](product-management/GLOSSARY.md) | Plain-language definitions for technical terms |

=== "Advanced"

    Research-grade content — architectures, papers, evaluation, and 100+ sources.

    | Section | What you'll find |
    |---------|-----------------|
    | [**AI Engineering**](ai-engineering/README.md) | LLM foundations, agentic AI, context engineering, full-stack development, AI services & APIs |
    | [**Design & Web**](design-knowledge/README.md) | UI principles, WCAG accessibility, design thinking, checkout/donations, backend API patterns |
    | [**All Sources**](sources.md) | 102 deduplicated references — research papers, vendor docs, practitioner content |
    | [**Companion Articles**](cursor-knowledge/README.md) | AI context reading lists, mobile web design, backlog philosophy |
    | [**Full onboarding catalog**](onboarding/INDEX.md) | Every guide with reading paths A–D |
    | [**Product Management**](product-management/README.md) | PM knowledge base, quality criteria, backlog practices |

---

## About

This knowledge base is maintained by **Victoria Crosby** ([@vcrosby22](https://github.com/vcrosby22)), a Technical Project Manager who uses Cursor daily and shares what works.

Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — share and adapt with attribution.

[View on GitHub :fontawesome-brands-github:](https://github.com/vcrosby22/ai-assisted-work){ .md-button }
