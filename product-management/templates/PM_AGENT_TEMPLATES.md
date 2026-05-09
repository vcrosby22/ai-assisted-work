# PM agent templates

Purpose: reusable output templates for AI product management workflows. Copy the relevant section into a new artifact or response, then fill with evidence and assumptions.

## Strategy brief

```markdown
# Strategy brief: <product / initiative>

## Decision Needed
<What decision this brief supports.>

## Context
- Product / area:
- Target customer:
- Business objective:
- Product outcome:
- Current evidence:
- Constraints:

## Customer Problem
<Who is struggling, what they are trying to accomplish, and why current options fall short.>

## Strategic Options
| Option | Customer value | Business value | Key risk | Evidence level |
|--------|----------------|----------------|----------|----------------|
| A | | | | |
| B | | | | |
| C | | | | |

## North Star Candidate
- North Star:
- Why it reflects customer value:
- Input metrics:

## Recommendation
<Recommended option and why.>

## Next Decision / Test
<Smallest next step that improves confidence.>
```

## Discovery brief

```markdown
# Discovery brief: <outcome / opportunity>

## Outcome
<Business or product outcome we are trying to move.>

## Target Segment
<Specific users/customers to learn from.>

## Known Evidence
- Qualitative:
- Quantitative:
- Competitive / market:
- Internal stakeholder signal:

## Opportunity Solution Tree
- Outcome:
  - Opportunity 1:
    - Solution candidate:
    - Assumption test:
  - Opportunity 2:
    - Solution candidate:
    - Assumption test:

## Riskiest Assumptions
| Assumption | Type | Why risky | Test | Decision rule |
|------------|------|-----------|------|---------------|
| | Desirability / viability / feasibility / usability / ethics | | | |

## Research / Test Plan
- Method:
- Participants / data source:
- Script or task:
- Timeline:
- Success / stop criteria:

## Next Decision
<What we will decide after learning.>
```

## Prioritization scorecard

```markdown
# Prioritization scorecard: <candidate set>

## Outcome Being Optimized
<Outcome, metric, or strategic theme.>

## Candidates
| Candidate | Reach | Impact | Confidence | Effort | RICE | Notes / override |
|-----------|-------|--------|------------|--------|------|------------------|
| | | | | | | |

## Non-Score Constraints
- Dependencies:
- Compliance / security:
- Customer commitments:
- Strategic bets:

## Recommended Order
1. <Candidate> — <reason>
2. <Candidate> — <reason>
3. <Candidate> — <reason>

## Evidence to Improve Confidence
<What to learn before committing larger effort.>
```

## Now / Next / Later roadmap

```markdown
# Roadmap: <product / area>

Audience: <exec / product trio / engineering / customer-facing>
Last updated: <date>

## Strategy Anchor
- Vision / theme:
- Business objective:
- Product outcome:

## Now
| Theme / problem | Outcome | Owner | Confidence | Notes |
|-----------------|---------|-------|------------|-------|
| | | | | |

## Next
| Theme / problem | Outcome | Owner | Confidence | Notes |
|-----------------|---------|-------|------------|-------|
| | | | | |

## Later
| Theme / problem | Outcome | Owner | Confidence | Notes |
|-----------------|---------|-------|------------|-------|
| | | | | |

## Not A Release Plan
<Any caveats about dates, confidence, dependencies, or separate delivery planning.>
```

## PRD

```markdown
# PRD: <feature / product>

## Summary
<One paragraph: problem, solution, target user, expected value.>

## Problem
- Target user:
- Pain / need:
- Evidence:
- Why now:

## Goals
- <Goal 1>
- <Goal 2>

## Non-Goals
- <What this explicitly will not solve.>

## Proposed Solution
<Solution narrative and key user flow.>

## Requirements
| ID | Requirement | Acceptance criteria | Priority |
|----|-------------|---------------------|----------|
| R1 | | | Must / Should / Could |

## Non-Functional Requirements
- Performance:
- Reliability:
- Security / privacy:
- Accessibility:
- Compliance:
- Analytics / instrumentation:

## Dependencies
- Product:
- Design:
- Engineering:
- Go-to-market / support:

## Success Metrics
- Primary:
- Secondary:
- Guardrail:

## Risks and Open Questions
| Item | Owner | Needed by | Decision / next step |
|------|-------|-----------|----------------------|
| | | | |
```

## Shape Up pitch

```markdown
# Shaped pitch: <idea>

## Problem
<What problem matters and for whom.>

## Appetite
<Time budget or level of investment we are willing to spend.>

## Shaped Solution
<High-level solution boundaries. Concrete enough to orient, abstract enough to leave room.>

## Rabbit Holes
- <Risk or tempting overbuild to avoid.>

## No-Gos
- <What is out of bounds for this bet.>

## Smallest Integrated Slice
<The first end-to-end slice that proves the shape works.>

## Success Signal
<How we know the bet paid off.>
```

## AI PM context packet

```markdown
# AI PM context packet: <task / product>

## Task Class
<single-call / workflow / agentic>

## Goal
<What the agent should accomplish.>

## Required Context
- Product / initiative:
- Target user:
- Business objective:
- Product outcome:
- Evidence:
- Constraints:
- Decision needed:
- Audience:

## Sources To Load
- <Repo file or URL>

## Tools / Interfaces
- <Files, MCP tools, analytics, issue tracker, docs, search, browser, etc.>

## Human Checkpoints
- <Where the agent must pause for approval or judgment.>

## Evaluation Criteria
- <How to judge the output.>

## Known Failure Modes
- <Hallucinated evidence, feature-first framing, overbroad context, etc.>
```

## Design brief

```markdown
# Design brief: <product / service / experience>

## Decision Needed
<What this design work should help decide.>

## Context
- Target user:
- Context of use:
- Business objective:
- Product outcome:
- Current evidence:
- Constraints:

## Problem Statement
<User, need, context, and why existing options fall short.>

## Design Method
<Design Thinking / UCD / HCD / Double Diamond / Service Design, and why this method fits.>

## Assumptions
| Assumption | Evidence level | Risk | Validation method |
|------------|----------------|------|-------------------|
| | | | |

## Candidate Directions
| Direction | User value | Business value | Risk | Test |
|-----------|------------|----------------|------|------|
| | | | | |

## Next Step
<Research, prototype, test, service blueprint, or stakeholder decision.>
```

## Double Diamond plan

```markdown
# Double Diamond plan: <challenge>

## Outcome
<Business/product outcome and user outcome.>

## Discover
- Research questions:
- Users / participants:
- Existing evidence:
- Methods:

## Define
- Key insights:
- Problem statement:
- Design principles:
- Decision criteria:

## Develop
- Concept directions:
- Co-design / ideation participants:
- Prototype approach:
- Assumptions to test:

## Deliver
- Test plan:
- Success criteria:
- Rejected options:
- Iteration plan:

## Next Checkpoint
<Who decides what, and when.>
```

## UCD / HCD checklist

```markdown
# UCD / HCD checklist: <product / flow>

## User And Context
- Primary users:
- Secondary users:
- Context of use:
- Accessibility or human factors considerations:

## Tasks And Goals
- User goal:
- Critical tasks:
- Current pain points:
- Environmental or operational constraints:

## Evidence
- Observed behavior:
- Research / analytics:
- Usability findings:
- Assumptions:

## Design Requirements
- Functional:
- Usability:
- Accessibility:
- Safety / privacy / trust:
- Measurement:

## Validation
- Prototype or test:
- Participants:
- Tasks:
- Success criteria:
- Guardrails:
```

## Service blueprint outline

```markdown
# Service blueprint: <journey / service>

## Scenario
- Customer goal:
- Business goal:
- Scope:
- Entry point:
- Exit point:

## Blueprint
| Journey stage | Customer actions | Frontstage actions | Backstage actions | Support processes | Evidence | Pain points / opportunities |
|---------------|------------------|--------------------|-------------------|-------------------|----------|-----------------------------|
| | | | | | | |

## Lines To Review
- Line of interaction:
- Line of visibility:
- Line of internal interaction:

## Dependencies
- People:
- Props / systems:
- Policies:
- Data:

## Improvement Bets
| Bet | Customer impact | Employee impact | Operational risk | Test |
|-----|-----------------|-----------------|------------------|------|
| | | | | |
```
