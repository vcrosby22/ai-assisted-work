# AI Assisted Work

Welcome to a **free, open collection** of guides, technical knowledge, and resources for learning [Cursor](https://www.cursor.com/) and AI-assisted work.

**Cursor** is a code editor with a built-in AI assistant. You don't need to be a developer to use it. People use Cursor to write, plan, research, build websites, and turn ideas into working prototypes — by talking to the assistant instead of writing code from scratch.

---

## Choose your path

=== "Beginner"

    **Never used Cursor or AI tools before?** Start here:

    1. [**Install Cursor & first steps**](onboarding/guides/installing-cursor-and-first-steps.md) — download, open a folder, first conversation
    2. [**Building with agentic AI**](onboarding/guides/building-with-agentic-ai-non-technical.md) — the mindset: you steer, the AI builds
    3. [**First-week checklist**](onboarding/checklists/first-week-cursor-non-technical.md) — a light daily plan for days 1–7

    **No coding experience needed.** These guides assume zero programming background.

=== "Intermediate"

    **Comfortable with Cursor, ready to go deeper?**

    - [**Working with AI context**](onboarding/guides/working-with-ai-context.md) — when to start a new chat, keeping the assistant accurate
    - [**Session playbook**](onboarding/guides/cursor-session-playbook.md) — terminal, GitHub, static sites, journaling
    - [**Git basics for non-developers**](onboarding/guides/git-basics-for-non-developers.md) — save versions, share on GitHub
    - [**Glossary**](product-management/GLOSSARY.md) — plain-language definitions for technical terms

=== "Advanced"

    **Engineer, researcher, or power user?**

    - [**AI Engineering knowledge base**](ai-engineering/README.md) — LLM foundations, agentic AI, context engineering, full-stack LLM, AI services (54 scholarly sources)
    - [**Context engineering deep dive**](ai-engineering/context-engineering.md) — the flagship article
    - [**Full onboarding catalog**](onboarding/INDEX.md) — every guide with reading paths
    - [**Source index**](ai-engineering/SOURCE_INDEX.md) — master bibliography of all 54 references

---

## Quick answers

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
    :   **Plan** mode thinks with you and proposes changes for your review. **Agent** mode edits files and runs commands directly. Use Plan when you want control, Agent when you trust the direction. See [Installing Cursor & first steps](onboarding/guides/installing-cursor-and-first-steps.md).

    **How do I share what I build?**
    :   Use Git to save versions and push to GitHub. From there you can share a repo link or publish a site with GitHub Pages. See [Git basics](onboarding/guides/git-basics-for-non-developers.md).

    **Can I customize how the assistant behaves?**
    :   Yes — Cursor supports rules files (`.cursor/rules/`), slash commands, and skills that shape the assistant's behavior per project. See the [Triggers & prompts](onboarding/guides/cursor-triggers-and-prompts.md) guide.

=== "Advanced"

    **What models does Cursor support?**
    :   Claude (Anthropic), GPT-4 (OpenAI), and others — selectable per conversation. Model availability depends on your plan tier. Cursor handles the API routing; you choose the model in the chat header.

    **What is context engineering and why does it matter?**
    :   Context engineering is the practice of designing the information environment an LLM operates in — what it sees, when, and how. It directly affects output quality, hallucination rates, and agent reliability. See the [deep dive](ai-engineering/context-engineering.md).

    **Can I fine-tune models or bring my own API keys?**
    :   Cursor uses its own API layer. You cannot point it at a custom fine-tuned endpoint today. For fine-tuning workflows, see the [full-stack LLM](ai-engineering/full-stack-llm.md) article — it covers training, serving, and evaluation outside the IDE.

    **How do I evaluate agent reliability?**
    :   Track accuracy over time, compare model outputs, and build evaluation harnesses. The [AI engineering knowledge base](ai-engineering/README.md) covers evaluation frameworks, and the [source index](ai-engineering/SOURCE_INDEX.md) links to key papers on LLM benchmarking.

---

## What's in this knowledge base

=== "Beginner"

    Focus on learning Cursor and building your first projects — no code or Git required.

    | Section | What's inside |
    |---------|--------------|
    | [**Getting Started**](onboarding/guides/installing-cursor-and-first-steps.md) | Install Cursor, have your first AI conversation, and follow a first-week plan |
    | [**Glossary**](product-management/GLOSSARY.md) | Plain-language definitions for technical terms you'll encounter |
    | [**Curated links**](onboarding/links/README.md) | Handpicked external resources on AI safety, privacy, and research literacy |

=== "Intermediate"

    You're using Cursor regularly — now learn to share work, manage context, and customize your setup.

    | Section | What's inside |
    |---------|--------------|
    | [**Getting Started**](onboarding/guides/installing-cursor-and-first-steps.md) | Guides, checklists, and reference for learning Cursor |
    | [**Guides & Reference**](onboarding/INDEX.md) | Git basics, triggers & prompts, slash commands, session playbooks |
    | [**Product Management**](product-management/README.md) | PM frameworks, glossary, backlog best practices |
    | [**Companion Articles**](cursor-knowledge/README.md) | AI context reading lists, mobile web UX, Git workflow patterns |

=== "Advanced"

    Deep technical content — LLM architectures, agent design, evaluation, and 100+ scholarly sources.

    | Section | What's inside |
    |---------|--------------|
    | [**AI Engineering**](ai-engineering/README.md) | LLM foundations, agentic AI, context engineering, full-stack LLM development, AI services & APIs |
    | [**Sources**](sources.md) | 102 deduplicated references — research papers, vendor docs, practitioner content |
    | [**Companion Articles**](cursor-knowledge/README.md) | AI context reading lists, mobile web design, backlog philosophy |
    | [**Full onboarding catalog**](onboarding/INDEX.md) | Every guide with reading paths A–D |
    | [**Product Management**](product-management/README.md) | PM knowledge base, quality criteria, backlog practices |

---

## About

This knowledge base is maintained by **Victoria Crosby** ([@vcrosby22](https://github.com/vcrosby22)), a Technical Project Manager who uses Cursor daily and shares what works.

Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — share and adapt with attribution.

[View on GitHub :fontawesome-brands-github:](https://github.com/vcrosby22/ai-assisted-work){ .md-button }
