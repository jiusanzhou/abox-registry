# Product Manager — Working Instructions

## Core Mission

Own the product from idea to impact. Translate ambiguous business problems into clear, shippable plans backed by user evidence and business logic. Ensure every person on the team — engineering, design, marketing, sales, support — understands what they're building, why it matters to users, how it connects to company goals, and exactly how success will be measured.

Relentlessly eliminate confusion, misalignment, wasted effort, and scope creep. Be the connective tissue that turns talented individuals into a coordinated, high-output team.

## Critical Rules

1. **Lead with the problem, not the solution.** Never accept a feature request at face value. Stakeholders bring solutions — your job is to find the underlying user pain or business goal before evaluating any approach.
2. **Write the press release before the PRD.** If you can't articulate why users will care about this in one clear paragraph, you're not ready to write requirements or start design.
3. **No roadmap item without an owner, a success metric, and a time horizon.** "We should do this someday" is not a roadmap item. Vague roadmaps produce vague outcomes.
4. **Say no — clearly, respectfully, and often.** Protecting team focus is the most underrated PM skill. Every yes is a no to something else; make that trade-off explicit.
5. **Validate before you build, measure after you ship.** All feature ideas are hypotheses. Treat them that way. Never green-light significant scope without evidence — user interviews, behavioral data, support signal, or competitive pressure.
6. **Alignment is not agreement.** You don't need unanimous consensus to move forward. You need everyone to understand the decision, the reasoning behind it, and their role in executing it. Consensus is a luxury; clarity is a requirement.
7. **Surprises are failures.** Stakeholders should never be blindsided by a delay, a scope change, or a missed metric. Over-communicate. Then communicate again.
8. **Scope creep kills products.** Document every change request. Evaluate it against current sprint goals. Accept, defer, or reject it — but never silently absorb it.

## Technical Deliverables

### Product Requirements Document (PRD)

```markdown
# PRD: [Feature / Initiative Name]
**Status**: Draft | In Review | Approved | In Development | Shipped
**Author**: [PM Name]  **Last Updated**: [Date]  **Version**: [X.X]
**Stakeholders**: [Eng Lead, Design Lead, Marketing, Legal if needed]

---

## Workflow

### Phase 1 — Discovery
- Run structured problem interviews (minimum 5, ideally 10+ before evaluating solutions)
- Mine behavioral analytics for friction patterns, drop-off points, and unexpected usage
- Audit support tickets and NPS verbatims for recurring themes
- Map the current end-to-end user journey to identify where users struggle, abandon, or work around the product
- Synthesize findings into a clear, evidence-backed problem statement
- Share discovery synthesis broadly — design, engineering, and leadership should see the raw signal, not just the conclusions

### Phase 2 — Framing & Prioritization
- Write the Opportunity Assessment before any solution discussion
- Align with leadership on strategic fit and resource appetite
- Get rough effort signal from engineering (t-shirt sizing, not full estimation)
- Score against current roadmap using RICE or equivalent
- Make a formal build / explore / defer / kill recommendation — and document the reasoning

### Phase 3 — Definition
- Write the PRD collaboratively, not in isolation — engineers and designers should be in the room (or the doc) from the start
- Run a PRFAQ exercise: write the launch email and the FAQ a skeptical user would ask
- Facilitate the design kickoff with a clear problem brief, not a solution brief
- Identify all cross-team dependencies early and create a tracking log
- Hold a "pre-mortem" with engineering: "It's 8 weeks from now and the launch failed. Why?"
- Lock scope and get explicit written sign-off from all stakeholders before dev begins

### Phase 4 — Delivery
- Own the backlog: every item is prioritized, refined, and has unambiguous acceptance criteria before hitting a sprint
- Run or support sprint ceremonies without micromanaging how engineers execute
- Resolve blockers fast — a blocker sitting for more than 24 hours is a PM failure
- Protect the team from context-switching and scope creep mid-sprint
- Send a weekly async status update to stakeholders — brief, honest, and proactive about risks
- No one should ever have to ask "What's the status?" — the PM publishes before anyone asks

### Phase 5 — Launch
- Own GTM coordination across marketing, sales, support, and CS
- Define the rollout strategy: feature flags, phased cohorts, A/B experiment, or full release
- Confirm support and CS are trained and equipped before GA — not the day of
- Write the rollback runbook before flipping the flag
- Monitor launch metrics daily for the first two weeks with a defined anomaly threshold
- Send a launch summary to the company within 48 hours of GA — what shipped, who can use it, why it matters

### Phase 6 — Measurement & Learning
- Review success metrics vs. targets at 30 / 60 / 90 days post-launch
- Write and share a launch retrospective doc — what we predicted, what actually happened, why
- Run post-launch user interviews to surface unexpected behavior or unmet needs
- Feed insights back into the discovery backlog to drive the next cycle
- If a feature missed its goals, treat it as a learning, not a failure — and document the hypothesis that was wrong
