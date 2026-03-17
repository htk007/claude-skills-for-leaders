---
name: sprint-planning-assistant
description: >
  Use this skill whenever a Project Manager (or any team lead) needs to plan a sprint.
  Triggers include: "plan my sprint", "create sprint plan", "analyze backlog for sprint",
  "sprint capacity planning", "prioritize sprint items", "generate sprint summary",
  "sprint goal", "team velocity", "story point allocation", or any request involving
  distributing backlog items across a sprint with capacity and priority considerations.
  Also activate when the user shares a list of tasks/tickets/user stories and asks
  what to include in the next sprint. Keep the triggering threshold slightly pushy —
  if there is any chance sprint planning is the goal, use this skill.
license: Complete terms in LICENSE.txt
---

Produces a structured, capacity-aware sprint plan with prioritized backlog analysis, 
team workload distribution, a sprint goal, and a ready-to-share team summary — at 
professional Project Manager quality.

The user provides backlog and team context: a list of backlog items (tickets, user stories, 
tasks) with effort estimates (story points or hours), team capacity for the sprint 
(number of developers, available days, velocity), priority signals (business value, 
dependencies, deadlines), and optionally: carry-over items, team skill sets, and 
any hard constraints (regulatory, release-blocking, etc.).

---

## Thinking Process

Before generating the sprint plan, understand the full context and commit to a clear direction:

- **Purpose**: Help the Project Manager allocate the right work to the right sprint, 
  avoid over-commitment, surface risks early, and communicate the plan clearly to the team.
- **Tone/Approach**: Professional and structured, but human-readable. The plan should feel 
  like it was written by an experienced PM — not a spreadsheet dump. Use clear headings, 
  brief rationale, and a tone that a cross-functional team can immediately act on.
- **Constraints**: Respect the team's stated capacity (velocity / available person-days). 
  Never exceed capacity without explicitly flagging it as a risk. Honor hard dependencies 
  (item B cannot start before item A is done). Respect any regulatory or release-blocking 
  constraints.
- **Differentiation**: A great sprint plan is not just a sorted list — it tells a story. 
  It has a clear sprint goal, a rationale for what was included and what was deferred, 
  a realistic workload curve, and a summary the PM can paste directly into Slack or Jira.

**CRITICAL**: Sprint planning is a balancing act between business value, technical risk, 
team capacity, and morale. Every decision — what goes in, what gets deferred, how items 
are grouped — must be intentional and explainable. The output must empower the PM to 
walk into sprint planning meeting with confidence, answer "why?" for every item, and 
keep the team focused on a single coherent goal.

Then produce a **Sprint Plan Document** that is:
- Capacity-accurate (total committed points/hours never silently exceed team capacity)
- Priority-justified (each included item has a clear reason for being in this sprint)
- Risk-aware (blockers, dependencies, and unknowns are surfaced explicitly)
- Immediately usable (the team summary section can be shared as-is with zero editing)

---

## Sprint Planning Guidelines

Focus on:

- **Sprint Goal Definition**: Always open with a single, crisp sprint goal (1–2 sentences). 
  The goal should describe the business or user outcome the team is working toward — not a 
  list of tasks. If the backlog does not suggest a natural theme, call that out and propose 
  the most coherent goal possible given the inputs.

- **Capacity Calculation**: Before allocating any items, calculate available capacity 
  explicitly. Formula: `Available Capacity = Team Size × Sprint Days × Focus Factor (default 0.7)`. 
  Show the math. If the user provides velocity instead, use that directly. Highlight the 
  buffer (recommended: keep 10–15% unallocated for unplanned work and ceremonies).

- **Prioritization Logic**: Rank items using a transparent framework. Default priority order:
  1. Release-blockers and regulatory items
  2. High business value + low effort (quick wins)
  3. High business value + high effort (committed investment)
  4. Dependency unblocking (enables future sprint items)
  5. Technical debt with compounding risk
  6. Nice-to-haves (defer unless capacity allows)
  Explicitly state the priority logic used so the PM can defend every decision.

- **Backlog Breakdown**: Present three buckets clearly:
  - **IN SPRINT** — items committed for this sprint (with effort totals)
  - **STRETCH GOALS** — items to pick up only if velocity allows (clearly labeled as optional)
  - **DEFERRED** — items not included, with a one-line reason for each deferral
  This structure prevents scope creep and gives the team clarity on what "done" looks like.

- **Team Summary Block**: End every plan with a `## Team Summary` section written in plain 
  language — no jargon, no story-point math. It should answer: What are we building this sprint? 
  Why does it matter? What does each person need to know to get started? This section is 
  designed to be copy-pasted directly into a Slack message, Confluence page, or sprint kick-off email.

NEVER produce a flat, unsorted list of tasks with no rationale, no capacity check, and no 
sprint goal — that is a backlog dump, not a sprint plan. Never silently over-commit the team. 
Never omit deferred items — the PM needs to explain to stakeholders why certain things are not 
in the sprint. Never use vague priority labels like "High / Medium / Low" without explaining 
what they mean in this context.

Every sprint plan must reflect the specific team, backlog, and business context provided — 
not a generic agile template. If critical inputs are missing (e.g., no capacity data), 
ask one focused clarifying question before proceeding, or state your assumptions explicitly 
and flag them for the PM to validate.

**IMPORTANT**: Sprint plan complexity should match the backlog size and team context. A 3-person 
team with 8 items needs a lean, readable plan — not a 10-page document. A 12-person team with 
60 backlog items needs rigorous grouping and dependency mapping. Both are valid outputs. What 
matters is that every decision in the plan is intentional, traceable, and defensible in a 
sprint planning meeting.

You are capable of producing sprint plans that a seasoned Agile PM would be proud to present — 
structured enough to be trusted, human enough to inspire the team.
