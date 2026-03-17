---
name: prd-writer
description: >
  Use this skill whenever a Product Manager needs to draft a Product Requirements Document from a brief,
  idea, or stakeholder request. Triggers include: phrases like "write a PRD for", "draft product requirements",
  "I need a PRD", "turn this brief into a PRD", "document requirements for this feature", "write up the
  spec for", "create a product spec", or any request where the user describes a product initiative and
  wants it formalized into a structured document ready for engineering, design, and stakeholder review.
  Also trigger when the user pastes a strategy note, an OKR, a customer insight summary, or an executive
  ask and wants it shaped into a full requirements document. If the input describes a product problem or
  initiative — however incomplete — default to producing a PRD draft rather than waiting for a perfect brief.
  A rough input is not a reason to pause; it is an opportunity to surface what still needs to be defined.
---

Produces a complete, stakeholder-ready Product Requirements Document from a rough brief — covering
problem statement, goals, scope, user requirements, success metrics, constraints, and open questions —
at the quality level expected in a cross-functional product review.

The user provides **a product brief or initiative description**: this can range from a single sentence
("we need to let users export their data") to a strategy doc excerpt, an OKR, a customer research
summary, an executive request, or a rough feature outline. The skill transforms whatever is given into
a structured PRD that engineering, design, and business stakeholders can act on.

## Thinking Process

Before drafting the PRD, understand the initiative and commit to a clear framing:

- **Purpose**: A PRD exists to align everyone — engineering, design, QA, marketing, legal, leadership —
  around what is being built, why it matters, and what success looks like. It is the single source of
  truth for a product initiative. A well-written PRD eliminates misalignment before it becomes a missed
  sprint, a wrong build, or a stakeholder surprise at launch.
- **Tone/Approach**: Clear, direct, and precise. A PRD is not a vision document — it is an operational
  contract. Write in plain language that a new engineer or a non-technical stakeholder can both parse.
  Avoid jargon without definition, passive voice, and hedged language ("might", "could", "possibly").
  Every sentence should carry information; filler erodes trust in the document.
- **Constraints**: The PRD must be complete enough to begin design and engineering scoping, but not
  so prescriptive that it dictates implementation. It defines *what* and *why* — not *how*. Scope
  boundaries must be explicit: what is in, what is out, and what is deferred. Open questions must be
  listed and owned, not buried or glossed over.
- **Differentiation**: Generic PRDs restate the feature request in structured form. A great PRD reframes
  the problem clearly, pressure-tests the goals against real user needs, surfaces constraints and risks
  the brief didn't mention, and writes success metrics that are actually measurable — not vanity proxies.
  It makes reviewers smarter about the initiative, not just informed of it.

**CRITICAL**: The PM is accountable for the quality of alignment this document creates. Vague goals
produce misaligned builds. Missing scope boundaries produce never-ending sprints. Unmeasured success
produces launches no one can evaluate. Every PRD produced by this skill must be specific enough that
two independently working teams would arrive at the same understanding of what to build and why. If
the input is too thin to achieve that, the PRD must make the gaps explicit in the Open Questions section
rather than papering over them with plausible-sounding filler.

Then produce a **Markdown PRD document** that is:
- Complete enough for a cross-functional kickoff meeting without supplementary explanation
- Precise in scope — every in-scope item named, every out-of-scope item explicitly excluded
- Honest about uncertainty — open questions surfaced with ownership assigned, not hidden
- Actionable — each section giving the reader something concrete to do, decide, or validate

---

## PRD Writing Guidelines

Focus on:

- **Problem Statement**: Open with a sharp, user-centered problem statement that answers: who is
  affected, what pain or friction they experience, what evidence supports this (data, research, support
  volume, competitive pressure), and what the cost of not solving it is. Avoid framing the problem as
  the absence of a feature ("users can't export data") — frame it as the user experience breakdown
  ("users who need their data for compliance reporting have no automated path, forcing manual workarounds
  that take hours and introduce error"). The problem statement sets the standard against which the
  solution will be judged.

- **Goals & Success Metrics**: State 2–4 outcome-oriented goals for the initiative. Each goal must
  be paired with at least one measurable success metric — a specific number, a before/after delta,
  or a defined threshold. "Improve user satisfaction" is not a goal; "Increase export feature adoption
  to 30% of eligible users within 60 days of launch, measured by event instrumentation" is. Distinguish
  between primary metrics (the initiative is judged by these) and guardrail metrics (these must not
  regress). If business goals and user goals are in tension, name that tension explicitly.

- **Scope Definition**: Define scope in three explicit lists — In Scope (what will be built in this
  initiative), Out of Scope (what will not be built, even if related), and Future Consideration (what
  is deferred to a later phase and why). This three-part structure is non-negotiable: "out of scope"
  and "future consideration" are different categories and must not be collapsed. Every scope decision
  should be a choice, not an omission.

- **User Requirements & Functional Specification**: Describe what the product must do from the user's
  perspective, organized by user flow or persona where relevant. Write requirements as observable
  behaviors ("a user can download their complete data history as a CSV file within 30 seconds of
  requesting it"), not system instructions ("the backend must generate a CSV export"). Include: primary
  happy path flows, key error and edge case behaviors, accessibility requirements, and any platform
  or device constraints. Reference wireframes or design links if available; flag where design is TBD.

- **Constraints, Dependencies & Risks**: Surface what the team is working within — technical constraints
  (existing architecture limitations, third-party API dependencies), regulatory or compliance requirements,
  resource or timeline constraints, and external dependencies (other teams, vendors, data readiness).
  Then list the top 3–5 risks to the initiative with an initial likelihood and impact assessment and
  a proposed mitigation or owner for each. Risks that are named are risks that can be managed.

- **Open Questions**: Close every PRD with a structured list of unresolved questions that must be
  answered before or during development. For each question: state the question clearly, identify who
  owns the answer, and set a target resolution date if known. Categorize questions as blocking (work
  cannot begin without an answer) or non-blocking (can be resolved in parallel). A PRD with no open
  questions is either unusually complete or hiding uncertainty — both deserve scrutiny.

NEVER produce a PRD that: restates the feature request as the problem statement without reframing it
as a user problem; writes success metrics that cannot be measured with available instrumentation;
collapses scope boundaries into a single vague "what's included" paragraph; uses requirements language
like "the system should" or "ideally the product would"; omits open questions to make the document
look more complete than it is; or produces a goals section where every goal is a feature shipped
rather than an outcome achieved.

A PRD is not a record of what was decided — it is a tool for making decisions. Every section should
provoke a reaction from its reader: agreement, challenge, or a question. A PRD that generates no
pushback in review is either perfectly written or hasn't been read carefully enough.

**IMPORTANT**: PRD depth should scale with initiative size. A small scoped feature improvement may
need two paragraphs per section and a single page total; a new product surface may need detailed
sub-sections, multiple personas, and a phased scope breakdown. Both are valid. What must never vary
is structural completeness: every PRD, regardless of length, must contain a problem statement, goals
with metrics, explicit scope boundaries, user requirements, and open questions. A short PRD that
covers all six dimensions is always preferable to a long PRD that covers four of them in detail.

A PM who writes PRDs at this standard earns credibility across every function they work with.
Engineering scopes more accurately. Design solves the right problem. Leadership approves with
confidence. QA knows what done looks like. That alignment does not happen by accident — it is
the direct result of a PM who did the thinking before the document, not during it.
