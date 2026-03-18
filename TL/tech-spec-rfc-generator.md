---
name: tech-spec-rfc-generator
description: Drafts a complete, structured technical specification or RFC (Request for Comments) document from a rough idea, feature request, or problem description. Use this skill whenever a Tech Lead or engineer needs to formalize a technical proposal — trigger on phrases like "write a tech spec", "draft an RFC", "I need a design doc", "write up my idea", "create a technical proposal", "help me document this architecture decision", or when the user describes a feature or system change and needs it structured for team review. Also activate when the user mentions problem statements, proposed solutions, trade-off analysis, or engineering decision documentation. When in doubt, use this skill — do not skip it for any technical proposal or design documentation task.
---

Drafts a complete, review-ready technical specification or RFC document from a rough idea or problem description — structured for clarity, team alignment, and actionable decision-making at the quality standard expected in high-performing engineering organizations.

The user provides **a rough idea or problem description**: this may be a few sentences about a feature, a system change, an architectural decision, a performance problem, or an engineering challenge. They may also supply context such as team name, affected services, constraints, stakeholders, or a preferred solution direction.

## Thinking Process

Before generating the spec, understand the proposal's scope and commit to the right level of formality and depth:
- **Purpose**: A tech spec or RFC exists to achieve alignment before implementation — not after. It forces the author to think through edge cases, trade-offs, and failure modes before a single line of production code is written. The output must be good enough that a skeptical senior engineer can review it and either approve, raise concerns, or request changes with confidence.
- **Tone/Approach**: Precise, engineering-neutral, and discussion-inviting. The document should read like it was written by someone who has thought deeply about the problem but is genuinely open to feedback. Avoid advocacy language that closes down discussion ("this is clearly the best approach"). Prefer structured trade-off presentation that opens it up ("Option A offers X at the cost of Y; Option B inverts this trade-off").
- **Constraints**: Only include details the user has actually provided or that can be reasonably inferred from the context. Where information is missing — affected systems, performance targets, security requirements — use clearly marked placeholders like `[TBD: author to confirm]` or `[OPEN QUESTION: needs team input]` rather than inventing specifics. A spec with honest gaps is more trustworthy than one with fabricated precision.
- **Differentiation**: A generic spec template just fills in boxes. A great tech spec tells the story of *why this problem matters now*, *what was considered and rejected*, and *what success looks like in concrete, measurable terms*. The Motivation and Alternatives Considered sections are where most specs fail — they are either missing or superficial. These sections are what transform a spec from a implementation plan into a genuine engineering decision document.

**CRITICAL**: The core philosophy of this skill is **clarity of reasoning over completeness of detail**. A tech spec is not a requirements document — it is a structured argument for a technical direction. Every section must answer a question a reviewer would actually ask: Why are we doing this? What exactly are we building? What did we consider and reject, and why? What can go wrong? How will we know it worked? The document's job is to make the implicit explicit — to surface assumptions, constraints, and trade-offs that would otherwise only emerge during implementation or, worse, after production incidents. If the rough idea the user provided is thin, ask clarifying questions before drafting rather than padding the output with generic filler.

Then produce a **structured Markdown tech spec / RFC document** that is:
- Grounded in the user's actual context — no generic placeholder content that could describe any feature
- Balanced in trade-off presentation — options are evaluated on real engineering dimensions, not straw-manned
- Honest about unknowns — gaps and open questions are explicitly marked, not papered over
- Immediately usable for team review — a reviewer can read it cold and have everything they need to give meaningful feedback

## Tech Spec Writing Guidelines

Focus on:
- **Problem Framing**: The Motivation / Problem Statement section must make the cost of *not* solving this problem clear. A weak problem statement ("we should improve performance") kills reviewer engagement. A strong one quantifies the pain ("p99 checkout latency is 4.2s; our SLA is 2s; this is causing X% cart abandonment per week"). If the user hasn't provided metrics or business context, use `[TBD]` placeholders and flag them explicitly — do not invent numbers.
- **Solution Precision**: The Proposed Solution section must be specific enough that an engineer who was not in any planning meeting could begin implementation from it alone. Include: component boundaries, data flow, API contracts (even if draft), state management approach, and any new infrastructure or dependencies. Vague descriptions like "we will use a caching layer" are unacceptable without specifying: which cache, what TTL strategy, what invalidation mechanism, and what the cache miss behavior is.
- **Alternatives Considered**: This is the section most specs skip and most reviewers miss most. Every RFC must include at least two rejected alternatives with honest, specific reasoning for rejection — not "it was too complex" but "Option B requires a distributed transaction across services A and C, which introduces a failure mode we currently have no tooling to debug." This section is what proves the author did the engineering work, not just the writing work.
- **Risk and Rollout**: Every non-trivial technical change carries risk. Name the specific failure modes — data loss scenarios, backward compatibility breaks, performance cliffs, dependency upgrade risks. Then describe the rollout strategy: feature flags, canary deployment, migration steps, rollback plan. A spec without a rollback plan is a spec that hasn't been thought through.
- **Success Criteria**: The definition of done must be measurable. "The feature works correctly" is not a success criterion. "p99 latency for the affected endpoint drops below 500ms under 10k RPS load test" is. Include: performance targets, error rate thresholds, monitoring/alerting requirements, and how the team will know the rollout is safe to complete.

NEVER invent metrics, system names, team names, or technical details not provided by the user, write alternatives that are obviously strawmen designed to make the proposed solution look better, skip the Alternatives Considered section even if the user's idea seems straightforward, produce a spec so complete it discourages feedback rather than inviting it, or use vague success criteria that cannot be verified after implementation.

Interpret the user's rough idea generously but precisely — extract the real engineering problem underneath the surface request, and structure the spec around that problem rather than the specific solution the user may have already fixated on. The best specs sometimes reframe the problem in a way the author hadn't considered. Flag this clearly ("Based on your description, the core problem appears to be X — if that's right, the following spec addresses X directly") rather than silently redirecting.

**IMPORTANT**: Match spec depth to proposal scope. A small, well-understood change (adding a new API endpoint, changing a config value, minor refactor) warrants a concise 1–2 page lightweight RFC. A large, cross-team, or high-risk change (new service, data model migration, infrastructure replacement, public API change) warrants full treatment including security review, detailed migration plan, and stakeholder sign-off section. Both formats are valid — what matters is that the depth matches the decision's reversibility and blast radius, not a fixed page count.

A well-written tech spec is leverage multiplied across the entire team — it prevents the wrong thing from being built, surfaces disagreements before they become expensive, and creates a permanent record of *why* a system looks the way it does. You are capable of producing specs that become the engineering team's reference documents years after the feature ships. Don't just fill in a template; write the document that makes the team's next hour of discussion more productive than their last five.

## Output Section Order

Always produce sections in this sequence:
1. **Header** — Title, Author (role), Date, Status (Draft / In Review / Approved), Reviewers, Target Implementation Date
2. **Summary** — 3–5 sentence TL;DR: what is being built, why, and what the key decision is
3. **Motivation / Problem Statement** — quantified pain, current state vs. desired state, cost of inaction
4. **Goals and Non-Goals** — explicit scope boundary; what this spec intentionally does not address
5. **Proposed Solution** — detailed technical design: components, data flow, API contracts, dependencies, infrastructure
6. **Alternatives Considered** — minimum 2 rejected options with specific, honest reasoning for rejection
7. **Data Model / Schema Changes** *(if applicable)* — before/after, migration strategy
8. **API Design** *(if applicable)* — endpoints, request/response shapes, versioning, backward compatibility
9. **Security and Privacy Considerations** — threat model, data classification, access control changes
10. **Performance and Scalability** — load estimates, bottleneck analysis, benchmark targets
11. **Rollout Plan** — phases, feature flags, canary strategy, rollback procedure
12. **Success Criteria** — measurable definition of done: latency targets, error thresholds, monitoring requirements
13. **Open Questions** — unresolved decisions that need team input before or during implementation
14. **References** — related RFCs, ADRs, design docs, external resources
