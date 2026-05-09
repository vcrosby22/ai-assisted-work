# AI PM workflows

Purpose: workflow library for an AI product management agent. Use this to route PM requests to the right process and artifact.

## Workflow router

| User asks for... | Use workflow | Primary output |
|------------------|--------------|----------------|
| "What should we build?" | Strategy framing | Strategy brief + decision options |
| "Understand users / discover opportunities" | Discovery planning | Discovery brief + interview/test plan |
| "Prioritize these ideas" | Prioritization | RICE / tradeoff scorecard |
| "Create a roadmap" | Roadmapping | Now/Next/Later roadmap |
| "Write a PRD / requirements" | Requirements | PRD + acceptance criteria |
| "Shape this project" | Delivery shaping | Shape Up-style pitch |
| "Design a product / apply design thinking / use UCD / map a service" | Design methodology | Design brief, Double Diamond plan, UCD/HCD checklist, or service blueprint |
| "Make an AI PM agent" | Context engineering | Agent context packet + workflow design |
| "Review a PM doc" | PM critique | Findings + risks + missing evidence |

## 1. Strategy framing

Use when the problem is broad, early, or ambiguous.

Inputs:
- Product vision or area.
- Target customer.
- Business objective.
- Current traction or evidence.
- Constraints and strategic bets.

Steps:
1. Translate the ask into a product outcome.
2. Identify the product "game" where useful: attention, transaction, or productivity.
3. Draft a North Star candidate and 3-5 input metrics.
4. Identify strategic options and tradeoffs.
5. Recommend the smallest next decision.

Output:
- Strategy brief.
- North Star tree.
- Decision options with evidence and risk.

Quality check:
- The metric should reflect realized customer value, not vanity activity.
- Options should be meaningfully different, not three phrasings of one answer.

## 2. Discovery planning

Use when deciding what problem to solve or validating whether a solution deserves build time.

Inputs:
- Desired outcome.
- Target segment.
- Existing research, analytics, support/sales signals.
- Candidate opportunities or solution ideas.

Steps:
1. Build an opportunity solution tree: outcome → opportunities → solutions → assumption tests.
2. Separate opportunities from solutions.
3. Identify assumptions across desirability, viability, feasibility, usability, and ethics.
4. Choose the lightest test that can reduce the biggest risk.
5. Define decision criteria before running the test.

Output:
- Discovery brief.
- Interview guide or assumption test plan.
- Opportunity solution tree in text form.

Quality check:
- The plan should include customers or real usage evidence, not only stakeholder opinions.
- The next test should be small enough to run soon.

## 3. Prioritization

Use when comparing opportunities, features, experiments, or roadmap candidates.

Inputs:
- Candidate list.
- Target outcome.
- Reach estimates.
- Impact hypothesis.
- Confidence evidence.
- Effort estimate.
- Dependencies and non-negotiables.

Steps:
1. Confirm the outcome being optimized.
2. Score RICE where useful: Reach × Impact × Confidence ÷ Effort.
3. Mark table-stakes, dependencies, deadlines, compliance, or customer commitments separately.
4. Compare rankings against strategy and qualitative risk.
5. Recommend ordering plus any explicit overrides.

Output:
- Prioritization table.
- Decision rationale.
- Follow-up evidence needed.

Quality check:
- Do not let weak confidence masquerade as precision.
- Explain any item selected out of score order.

## 4. Roadmapping

Use when aligning stakeholders on future direction.

Inputs:
- Vision or strategic theme.
- Audience.
- Time horizon.
- Key outcomes.
- Known initiatives.
- Confidence and dependencies.

Steps:
1. Choose audience depth: executive, product trio, engineering, sales/customer-facing.
2. Organize by Now / Next / Later unless another cadence is required.
3. Express roadmap items as problems, themes, or outcomes before features.
4. Add confidence, owner, and evidence where useful.
5. Separate delivery dates into a release plan if needed.

Output:
- Now / Next / Later roadmap.
- Roadmap notes: assumptions, dependencies, confidence, audience caveats.

Quality check:
- Roadmap should not become a sprint board.
- Items should ladder up to strategy or outcomes.

## 5. Requirements / PRD

Use when a solution is sufficiently shaped to align build, design, go-to-market, and stakeholder expectations.

Inputs:
- Problem statement.
- Target users.
- Goals and non-goals.
- Proposed solution.
- Functional and non-functional requirements.
- UX notes.
- Dependencies.
- Success metrics.

Steps:
1. Confirm the problem and outcome before describing the solution.
2. State goals, non-goals, and scope boundaries.
3. Capture functional requirements and acceptance criteria.
4. Capture non-functional requirements: performance, reliability, security, privacy, compliance, accessibility.
5. Identify launch, analytics, and support needs.
6. Mark open questions and decisions.

Output:
- PRD.
- Acceptance criteria.
- Measurement and launch checklist.

Quality check:
- Avoid fake certainty. Put unsettled decisions in open questions.
- Requirements should be testable or reviewable.

## 6. Delivery shaping

Use when an idea needs boundaries before committing engineering time.

Inputs:
- Raw idea.
- Appetite or time budget.
- Core user flow.
- Known rabbit holes.
- Technical constraints.
- Definition of "good enough."

Steps:
1. Set the appetite before estimating the full ideal solution.
2. Define the shaped solution at the right abstraction level.
3. Call out risks, rabbit holes, and no-gos.
4. Identify the smallest integrated slice.
5. Write a pitch for betting or rejection.

Output:
- Shaped pitch.
- Appetite, boundaries, risks, and success signal.

Quality check:
- A shaped pitch should leave room for builders to solve details.
- If the scope cannot fit the appetite, reduce scope before asking for more time.

## 7. Design methodology

Use when the task is about designing a product, service, workflow, user experience, or customer/employee journey.

Inputs:
- Product or service area.
- Target user and context of use.
- Customer journey or task.
- Business/product outcome.
- Existing evidence and open assumptions.
- Operational dependencies or backstage teams.

Steps:
1. Classify the design job: problem framing, solution exploration, validation, or service-system alignment.
2. Choose the method:
   - Double Diamond for divergent/convergent problem and solution work.
   - Design Thinking for empathize/define/ideate/prototype/test loops.
   - UCD/HCD for user goals, tasks, context, usability, accessibility, and human-system constraints.
   - Service Design for cross-functional journeys with frontstage/backstage dependencies.
3. Capture the current evidence and missing research.
4. Generate the design artifact: brief, plan, checklist, prototype/test plan, or service blueprint.
5. Define decision criteria before narrowing solutions.
6. Recommend the next test or stakeholder review.

Output:
- Design brief.
- Double Diamond plan.
- UCD/HCD checklist.
- Service blueprint outline.
- Prototype or usability test plan.

Quality check:
- Do not jump to UI screens before defining the user, context, problem, and evidence.
- Separate customer-facing touchpoints from backstage processes when the service spans teams.
- Make divergence and convergence explicit.

## 8. PM context engineering

Use when creating or improving an AI PM agent, skill, workflow, or knowledge base.

Inputs:
- Agent purpose.
- Task classes.
- Knowledge sources.
- Tools and permissions.
- Human checkpoint needs.
- Failure modes.

Steps:
1. Classify tasks as single-call, workflow, or agentic.
2. Define the minimum context packet for each task class.
3. Create routing rules to load only relevant context.
4. Define tool/document interfaces clearly.
5. Add evaluation criteria and human checkpoints.
6. Store durable context in repo files, not only chat history.

Output:
- Agent operating context.
- Workflow router.
- Templates.
- Evaluation checklist.

Quality check:
- Context should be inspectable, versioned, and easy for another agent to load.
- Add complexity only where it improves output quality or reliability.

## 9. PM artifact review

Use when asked to review a PRD, roadmap, strategy brief, backlog, discovery plan, or AI PM output.

Review for:
- Unclear user/customer.
- Weak or missing business/product outcome.
- Feature-first framing.
- Unsupported evidence.
- Missing risks or assumptions.
- Roadmap/release-plan confusion.
- Untestable requirements.
- Missing non-functional requirements.
- Missing design-methodology fit when the work involves users, services, or journeys.
- Stakeholder/audience mismatch.

Output:
- Findings first, ordered by severity.
- Open questions.
- Concise improvement plan.
