# AI PM agent resource pack — 2026-05-09

Purpose: fresh source pack for building an **AI product management agent** with durable product-management context, workflows, and templates. This complements the existing 2026-03-19 source index instead of replacing it.

Harvest method: web fetch + human synthesis. Do not paste raw article text into prompts by default; retrieve this index first, then load the specific workflow or template needed for the task.

## Quality bar

Sources were selected because they are widely cited, primary or near-primary, practical, and directly useful for one or more AI PM capabilities: strategy, discovery, roadmapping, prioritization, requirements, delivery shaping, measurement, or context engineering.

## Fresh resources


| #   | Source                                                                                                                                                            | Category               | Agent-useful takeaway                                                                                                                                                                           |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | [SVPG — The Product Operating Model](https://svpg.com/the-product-model/)                                                                                         | Operating model        | Product work is a way of working: principles, practices, and competencies that move companies away from project/IT/feature-output models. Use this as the top-level orientation for the agent.  |
| 2   | [SVPG — Product vs Feature Teams](https://www.svpg.com/product-vs-feature-teams/)                                                                                 | Team model             | Distinguish empowered product teams from feature teams. The agent should ask whether it is solving an outcome or merely documenting a requested feature.                                        |
| 3   | [Product Talk — Product Discovery Basics](https://www.producttalk.org/2021/08/product-discovery/)                                                                 | Discovery              | Discovery is decision-making about what to build. Strong teams stay continuously connected to customers and start from outcomes, opportunities, and solutions.                                  |
| 4   | [Product Talk — Opportunity Solution Trees](https://www.producttalk.org/2021/04/opportunity-solution-trees/)                                                      | Discovery structure    | Use outcome → opportunities → solutions → assumption tests to preserve traceability from business goals to build candidates.                                                                    |
| 5   | [Intercom — RICE Prioritization](https://www.intercom.com/blog/rice-simple-prioritization-for-product-managers/)                                                  | Prioritization         | Score Reach, Impact, Confidence, and Effort to compare unlike ideas. Treat the score as decision support, not an automatic mandate.                                                             |
| 6   | [NN/g — UX Roadmaps](https://www.nngroup.com/articles/ux-roadmaps/)                                                                                               | Roadmapping            | A roadmap is a living strategic artifact organized by scope, time horizon, and themes. Roadmaps should focus on problems/outcomes, not feature release plans.                                   |
| 7   | [Amplitude — North Star Metric](https://amplitude.com/blog/product-north-star-metric)                                                                             | Metrics / strategy     | A North Star metric should align to customer value, express product strategy, and lead future business outcomes. Use input metrics to make it actionable.                                       |
| 8   | [Atlassian — Product Roadmaps](https://www.atlassian.com/agile/product-management/product-roadmaps)                                                               | Roadmapping            | Roadmaps are shared sources of truth connecting vision, direction, priorities, and progress. Tailor detail by audience and update only as often as needed to preserve trust.                    |
| 9   | [Basecamp — Shape Up introduction](https://basecamp.com/shapeup/0.3-chapter-01)                                                                                   | Delivery shaping       | Shape before betting: define boundaries, appetite, risks, and the rough solution shape before committing team time. Useful when the agent needs to turn ambiguity into a bounded pitch.         |
| 10  | [DigitalOcean — Product Requirements Document](https://www.digitalocean.com/resources/articles/product-requirements-document)                                     | Requirements           | A PRD should align stakeholders around problem, objectives, audience, scope, functional/non-functional requirements, dependencies, and delivery expectations without becoming unreadable.       |
| 11  | [IdeaPlan — Context Engineering for Product Managers](https://www.ideaplan.io/blog/context-engineering-for-product-managers)                                      | PM context engineering | Context engineering is deciding what information an AI system receives, when, and in what structure. PM context should include user, business, competitive, technical, and interaction context. |
| 12  | [Anthropic — Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents)                                                          | Agent design           | Prefer simple, composable workflows before autonomous agents. Use workflows for predictable PM tasks and agents for open-ended work with clear checkpoints and ground truth.                    |
| 13  | [Martin Fowler / Thoughtworks — Context Engineering for Coding Agents](https://martinfowler.com/articles/exploring-gen-ai/context-engineering-coding-agents.html) | Context engineering    | Treat files, rules, skills, tools, MCP servers, subagents, and hooks as context interfaces. Keep context small, explicit, and loaded only when relevant.                                        |


## Synthesis for the AI PM agent

### Core operating principles

- Start from **outcomes**, not requested features. If the request is a feature, translate it into the customer problem, business outcome, and assumptions.
- Preserve traceability: business outcome → product outcome → customer opportunity → solution candidate → assumption test → requirement → release signal.
- Separate strategic artifacts from delivery artifacts. Roadmaps align on direction; PRDs align on what is being built; backlogs sequence execution.
- Treat prioritization frameworks as structured judgment. RICE, MoSCoW, Kano, and North Star inputs reveal tradeoffs; they do not replace product judgment.
- Design context as a product. The agent should load only the context needed for the PM job at hand and should cite the source or template it used.

### Minimum context packet for PM work

Every AI PM workflow should try to collect or infer:

1. Product / initiative name.
2. Target user or customer segment.
3. Business goal and product outcome.
4. Current evidence: user research, analytics, sales/support signal, competitive signal, technical constraints.
5. Decision needed now.
6. Known assumptions and risks.
7. Stakeholders and audience for the output.
8. Source artifacts already available in the repo.

### Capability map


| Capability               | Primary sources                        | Output artifact                                        |
| ------------------------ | -------------------------------------- | ------------------------------------------------------ |
| Product strategy framing | SVPG, Amplitude                        | Strategy brief, North Star tree                        |
| Discovery planning       | Product Talk, SVPG                     | Discovery brief, opportunity solution tree             |
| Prioritization           | Intercom, Kano/MoSCoW from existing KB | Prioritization scorecard                               |
| Roadmapping              | NN/g, Atlassian                        | Now/Next/Later roadmap                                 |
| Requirements             | DigitalOcean, Aha from prior index     | PRD, acceptance criteria                               |
| Delivery shaping         | Basecamp Shape Up                      | Shaped pitch, appetite, risks                          |
| Agent context design     | IdeaPlan, Anthropic, Martin Fowler     | Context packet, workflow routing, evaluation checklist |


## Gaps to hydrate next

- Primary Amazon Working Backwards / PR-FAQ source.
- HEART framework primary source or reliable Google Ventures reference.
- Product analytics instrumentation and experimentation playbooks.
- Product ethics / responsible AI decision frameworks beyond NIST and OWASP.
- Customer interview repository structure and insight tagging conventions.

