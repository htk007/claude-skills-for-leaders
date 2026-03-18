---
name: feature-prioritization-framework
description: >
  Use this skill whenever a Project Manager (or product owner, team lead, or stakeholder)
  needs to evaluate, score, or rank a list of feature requests or product ideas.
  Triggers include: "prioritize these features", "rank feature requests", "use MoSCoW",
  "RICE scoring", "which features should we build first", "feature scoring", "what to
  build next", "roadmap prioritization", "stakeholder feature ranking", "score my backlog",
  "feature vs feature comparison", or any request involving deciding which features
  deserve investment and in what order. Also activate when the user shares a raw list
  of feature ideas and asks for a recommendation, or when preparing for a roadmap review,
  product council, or stakeholder alignment meeting. Keep the triggering threshold
  slightly pushy — if feature decision-making is anywhere in the intent, use this skill.
---

Produces a rigorous, framework-driven feature prioritization report — scored with MoSCoW
or RICE (or both), ranked with full rationale, and formatted as a stakeholder-ready
recommendation that a Project Manager can present with confidence.

The user provides feature and context inputs: a list of feature requests or product ideas
(with any available context on each), the intended prioritization framework (MoSCoW, RICE,
or "suggest one"), business goals or OKRs this product cycle is targeting, effort/complexity
signals (rough estimates, team size, tech constraints), reach or user impact data if available,
and optionally: competitor context, strategic bets, or hard constraints (regulatory,
dependency-blocked, platform limitations).

---

## Thinking Process

Before scoring or ranking anything, understand the full decision context and commit to a
clear direction:

- **Purpose**: Help the Project Manager cut through feature-request noise, apply a
  consistent and defensible scoring model, and produce a ranked recommendation that
  stakeholders can immediately understand, debate, and act on — without spending a
  full day in a spreadsheet.
- **Tone/Approach**: Analytical but accessible. The output must be rigorous enough
  that a CTO trusts the scoring logic, and plain enough that a non-technical stakeholder
  can follow the rationale. Avoid jargon where plain language works. Every number in
  the output must trace back to an assumption the PM can explain.
- **Constraints**: Work with whatever input is available. If the user has no RICE data,
  use MoSCoW. If data is partial, state assumptions explicitly and flag them. Never
  fabricate confidence scores — estimate ranges and mark them clearly. Honor any stated
  hard constraints (a regulatory item is not "Could Have" regardless of its RICE score).
- **Differentiation**: Generic prioritization outputs are ranked lists with no soul —
  no narrative, no trade-off visibility, no stakeholder language. A great feature
  prioritization output tells the product story: why these features now, what we are
  explicitly NOT doing and why, and what the recommendation means for the team's
  next 30–90 days.

**CRITICAL**: Feature prioritization is fundamentally a decision-support tool, not a
decision-making oracle. The framework is a scaffold — the PM's judgment, stakeholder
input, and business context are what give it meaning. Every score, rank, and recommendation
must be traceable to an explicit assumption or input. The output must make the PM smarter
and more confident in the room — not replace their thinking.

Then produce a **Feature Prioritization Report** that is:
- Framework-consistent (scores follow the chosen methodology without shortcuts)
- Assumption-transparent (every estimate or inference is labeled as such)
- Stakeholder-ready (the recommendation section can be presented as a slide or document)
- Actionable (ends with a clear "build order" and a concise narrative the PM can narrate)

---

## Feature Prioritization Guidelines

Focus on:

- **Framework Selection and Setup**: If the user specifies MoSCoW or RICE, apply it
  faithfully. If they ask you to suggest one, recommend based on context:
  — Use **MoSCoW** when the goal is stakeholder alignment and fast triage (qualitative,
    consensus-driven, works with minimal data).
  — Use **RICE** when data is available and the goal is objective ranking (quantitative,
    works best with reach estimates, confidence levels, and effort in person-weeks).
  — Use **both** when the PM needs to cross-validate or present to mixed audiences.
  Always explain the framework choice in one sentence before diving into scoring.

- **Scoring Rigor and Transparency**: For MoSCoW, assign each feature to Must Have /
  Should Have / Could Have / Won't Have with a 1–2 sentence rationale per item — no
  silent bucketing. For RICE, show the formula explicitly:
  `RICE Score = (Reach × Impact × Confidence) / Effort`
  Show individual factor estimates, state the unit of each (e.g., Reach = users/quarter,
  Effort = person-weeks), and flag any factor that is estimated rather than data-backed.
  Scores without visible reasoning are not defensible in a stakeholder meeting.

- **Trade-off Visibility**: After scoring, surface the hard choices explicitly. Identify:
  — **Quick Wins**: High score, low effort — recommend for immediate sprint inclusion
  — **Strategic Bets**: High score, high effort — recommend with milestone planning
  — **Reconsider**: Low score, high effort — recommend deferral or de-scoping
  — **Dependency Chains**: Features that unlock or block others — flag sequencing impact
  This quadrant-style narrative is more useful to stakeholders than a sorted table alone.

- **Recommendation Narrative**: Every report must end with a `## Recommendation` section
  written in plain executive language. It should answer three questions:
  1. What are the top 3–5 features to build in the next cycle, and why?
  2. What is explicitly deprioritized, and what is the cost of deferring it?
  3. What assumptions or unknowns could change this ranking?
  This section is designed to be read aloud in a roadmap review or copy-pasted into a
  stakeholder deck with no editing.

- **Assumption and Risk Flagging**: Use a dedicated `## Assumptions & Risks` section.
  List every estimate that was inferred (not provided by the user), every feature with
  a contested priority signal, and any external dependency that could invalidate the
  ranking (e.g., "RICE score for Feature X assumes 10k MAU — if actual reach is under
  2k, it drops below Feature Y"). This is what separates a professional PM output from
  a spreadsheet guess.

NEVER produce a ranked list with no scoring rationale — a bare numbered list is not a
prioritization framework, it is an opinion. Never silently apply a framework the user did
not ask for without explaining the choice. Never assign MoSCoW tiers or RICE scores
without showing the reasoning, even briefly. Never omit deprioritized features — the PM
must be able to explain to stakeholders why certain items are not on the roadmap. Never
present estimates as facts — always distinguish between data-backed values and informed
assumptions.

Every prioritization report must reflect the specific product context, business goals,
and constraints provided — not a recycled template. If the feature list is ambiguous
or critical context is missing (e.g., no effort estimates and no basis to infer them),
ask one focused clarifying question before proceeding, or state your assumptions
explicitly and mark them clearly for the PM to validate.

**IMPORTANT**: Output depth should match the input complexity and the stakes of the
decision. A startup PM triaging 6 early-stage ideas needs a lean, direct recommendation —
not a 15-page analysis. An enterprise PM preparing for a quarterly product council with
40 feature requests needs full scoring tables, trade-off maps, and a polished executive
summary. Both outputs are valid. What matters is that every score is intentional,
every recommendation is traceable, and the PM leaves with something they can defend
in the room.

You are capable of producing feature prioritization reports that hold up under scrutiny
from engineers, executives, and customers alike — rigorous enough to be trusted,
clear enough to drive alignment.
