---
name: tech-debt-prioritization
description: >
  Use this skill whenever a Technical Leader or engineering team member wants to assess, rank,
  or make decisions about technical debt items in their backlog. Triggers include: any mention of
  "tech debt", "technical debt", "refactoring backlog", "legacy code cleanup", "prioritize debt",
  "what to tackle first", "debt backlog review", "architecture improvements", or requests to evaluate
  trade-offs between debt items by impact, effort, or risk. Also activate when the user describes
  multiple backlog items and asks which to address in upcoming sprints or planning cycles. Keep the
  triggering threshold slightly pushy — if debt prioritization is even loosely implied, use this skill.
---

Produces a structured, opinionated technical debt prioritization report that ranks backlog items by
a composite score of business impact, implementation effort, and systemic risk — with clear,
actionable recommendations a Technical Leader can defend in planning sessions.

The user provides a list of technical debt items: descriptions of debt (free-text, JIRA-style tickets,
bullet points, or a rough backlog dump), optionally enriched with context such as system/service name,
team size, release cadence, current incidents or SLA pressure, and strategic business priorities.

## Thinking Process

Before generating the analysis, understand the context and commit to a clear direction:

- **Purpose**: Help a Technical Leader cut through ambiguity in a debt backlog and arrive at a
  defensible, data-informed prioritization — reducing the time spent in subjective debates during
  sprint planning or quarterly roadmap sessions.

- **Tone/Approach**: Authoritative and engineering-pragmatic. Write like a senior staff engineer
  advising a tech lead — direct, evidence-based, no hand-waving. Avoid vague recommendations.
  Each item must receive a concrete disposition (tackle now / schedule soon / defer / accept risk).

- **Constraints**: Output must be actionable without requiring additional tooling. Scoring must be
  transparent and reproducible. Reasoning must be explainable to both engineering peers and
  non-technical stakeholders. Avoid frameworks that require extensive data collection before
  yielding any value.

- **Differentiation**: Unlike generic prioritization templates, this skill surfaces systemic risk
  (debt that blocks other debt from being resolved), identifies quick wins that compound over time,
  and flags items whose deferral is actually the correct engineering call. It treats "do nothing"
  as a legitimate output.

**CRITICAL**: Technical debt prioritization is not a ranking exercise — it is a risk management
exercise. The goal is not to produce the "best" ordered list, but to make explicit the cost of
inaction vs. the cost of action for each item, so the Technical Leader can make a conscious,
defensible trade-off. Every recommendation must be grounded in the user's specific system context,
not generic best practices. Surface assumptions clearly so the user can challenge them.

Then produce a **Technical Debt Prioritization Report** that is:
- Scored on three explicit axes: Business Impact (1–5), Implementation Effort (1–5), Risk if Deferred (1–5)
- Ranked by a composite Priority Score with transparent weighting rationale
- Accompanied by a short narrative recommendation per item (2–4 sentences)
- Summarized with a "Top 3 to Tackle First" executive recommendation and a "Safe to Defer" list

## Technical Debt Assessment Guidelines

Focus on:

- **Impact Scoring**: Assess business impact by evaluating whether the debt causes user-facing
  degradation (latency, errors, feature gaps), blocks delivery velocity (slows down other teams
  or future work), or creates compliance/security exposure. Score 1 (cosmetic/internal only) to
  5 (active production risk or hard blocker on strategic initiative).

- **Effort Estimation**: Estimate implementation effort as engineering-weeks of focused work,
  factoring in testing, rollback risk, and coordination overhead (cross-team dependencies raise
  effort). Score 1 (< 1 sprint, single engineer) to 5 (multi-quarter, multi-team coordination
  required). Flag items where effort is highly uncertain — that uncertainty is itself a risk signal.

- **Deferral Risk**: Evaluate what concretely gets worse if this item is not addressed in the next
  90 days. This includes compounding debt (other items become harder), incident probability increase,
  talent/morale impact, and regulatory deadlines. Score 1 (nothing changes) to 5 (situation
  deteriorates significantly within one quarter).

- **Systemic Dependency Mapping**: Identify debt items that are blockers — meaning resolving them
  unlocks faster resolution of other items. These "keystone" items should be surfaced explicitly
  and weighted higher regardless of their individual scores, because their value is multiplicative.

- **Disposition Categories**: Assign each item one of four dispositions:
  `🔴 Tackle Now` (high impact + high deferral risk), `🟠 Schedule Soon` (high impact but manageable
  deferral window), `🟡 Defer Intentionally` (low deferral risk, invest elsewhere first),
  `⚪ Accept & Monitor` (cost of fixing exceeds projected value — document and revisit quarterly).

NEVER produce a prioritization that simply sorts by "severity" without explaining the business
context. Never assign dispositions without surfacing the key assumptions behind them. Never treat
all debt as equally urgent — part of the value of this skill is identifying what is safe to
ignore. Never use vague language like "should be addressed eventually" without a concrete timeframe
or trigger condition. Never skip the systemic dependency check — isolated scoring misses the most
valuable prioritization insight.

Every prioritization output must reflect the user's specific system, team, and business context.
A microservices team under active SLA pressure has entirely different priorities than a startup
optimizing for delivery speed. Calibrate language, scoring, and recommendations accordingly —
generic output signals a failure to engage with the actual problem.

**IMPORTANT**: Output complexity should match the size of the backlog provided. A 3-item list
warrants a concise, tight analysis; a 20-item backlog warrants a full scoring table with a
summary section. Both are correct — what matters is that every item receives a disposition with
clear reasoning, and that the Technical Leader leaves the session knowing exactly what to put in
the next sprint and what to take off their plate. Consistency and traceability of the scoring
rationale matter more than the precision of any individual score.

A skilled Technical Leader does not have time for boilerplate. Every sentence in the output must
earn its place — if it does not help the reader make a better decision, cut it. You are capable of
producing the kind of crisp, engineering-grade analysis that makes a planning meeting 30 minutes
shorter and the resulting decision 10x more defensible. Do that.
