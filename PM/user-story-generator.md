---
name: user-story-generator
description: >
  Use this skill whenever a Product Manager needs to turn a rough feature idea into structured user stories
  ready for sprint grooming. Triggers include: phrases like "write user stories for", "turn this into a
  user story", "break this feature down", "I need stories for sprint", "write acceptance criteria for",
  "groom this feature", "story-fy this idea", or any request where the user describes a product feature,
  improvement, or requirement and wants it shaped into sprint-ready format. Also trigger when the user
  pastes a feature brief, a Jira ticket stub, a customer complaint, or a stakeholder request and asks
  for it to be structured. If the input resembles a product idea — however rough — default to producing
  user stories rather than asking for clarification first.
---

Produces a set of well-structured, sprint-ready user stories from a rough feature idea — each with a
clear role/goal/benefit format, granular acceptance criteria, and enough definition for a development
team to estimate and implement without ambiguity.

The user provides **a feature idea or requirement**: this can range from a single sentence ("add dark
mode to the app") to a paragraph description, a customer quote, a stakeholder email excerpt, or a
partially filled ticket. The skill transforms whatever is given into a complete, grooming-ready story set.

## Thinking Process

Before writing the stories, understand the feature and commit to a clear scope:

- **Purpose**: These stories exist to give the development team unambiguous, estimable units of work —
  and to give the PM a shared language with engineering and QA. A good story eliminates the need for
  a meeting to clarify intent. It should answer: who wants this, what they want, why they want it, and
  exactly what "done" looks like.
- **Tone/Approach**: Precise and user-centered. Write from the perspective of the end user or persona,
  not the internal system. Language should be clear enough for a junior developer to understand and
  specific enough for a QA engineer to write test cases from. Avoid technical implementation details
  in story titles — focus on behavior and outcome.
- **Constraints**: Stories must be independently deliverable where possible (INVEST principle: Independent,
  Negotiable, Valuable, Estimable, Small, Testable). Acceptance criteria must be binary — either the
  criterion is met or it isn't. Avoid acceptance criteria that require judgment calls ("the UI looks
  good") without a measurable definition.
- **Differentiation**: Generic story generators produce syntactically correct but semantically empty
  stories. This skill produces stories that reflect the *actual user goal*, surface *edge cases* the
  PM may not have considered, and write acceptance criteria precise enough to prevent scope creep
  during development.

**CRITICAL**: The PM's job is to represent the user's intent faithfully and give the engineering team
enough clarity to move without constant interruption. Every story produced by this skill must pass the
"desk check": could a developer pick this up cold, implement it, and know with certainty when it's done?
If the answer is no — because the acceptance criteria are vague, the scope is ambiguous, or the "why"
is missing — the story is not ready. Write stories that pass the desk check every time.

Then produce a **Markdown user story document** that is:
- Immediately usable in a sprint grooming session without further editing
- Scoped correctly — neither too large to estimate nor too small to be meaningful
- User-centered in framing, with the benefit ("so that...") always explicit and specific
- Complete — every story accompanied by acceptance criteria, edge cases, and any relevant notes

---

## User Story Writing Guidelines

Focus on:

- **Story Format**: Always use the canonical three-part structure:
  `As a [role], I want [goal], so that [benefit].`
  The role must be a real persona or user type (not "the system" or "the admin" unless that is genuinely
  the actor). The goal must describe behavior, not a feature toggle. The benefit must be specific —
  "so that I can save time" is weak; "so that I can complete checkout without re-entering my address
  on every order" is strong.

- **Story Decomposition**: If the feature idea is large, break it into multiple vertical slices — each
  delivering end-to-end user value, not horizontal layers (e.g., don't separate "frontend story" from
  "backend story" unless explicitly required). Each story in the set should stand alone as a shippable
  increment. Label stories with a logical sequence if order matters (Story 1 of 3, etc.).

- **Acceptance Criteria**: Write in Given/When/Then format wherever applicable:
  `Given [precondition], When [action], Then [outcome].`
  Each criterion must be independently verifiable by QA. Include: the happy path, at least one
  negative/failure case, boundary conditions, and any relevant accessibility or performance thresholds.
  Aim for 3–6 criteria per story; more than 8 is a sign the story should be split.

- **Edge Cases & Notes**: After the acceptance criteria, include a brief "Notes / Edge Cases" section
  flagging: known unknowns the PM should resolve before grooming, dependencies on other stories or
  systems, out-of-scope items (to prevent scope creep), and any open design or copy decisions.

- **Definition of Done Alignment**: Where relevant, add a one-line reminder of any team-level DoD
  items that apply (e.g., "Requires accessibility audit", "Needs analytics event instrumentation",
  "Must include error state in design review") so nothing is missed at sprint close.

NEVER produce stories that: use passive voice or system-centric framing ("the system shall..."); write
acceptance criteria as feature descriptions rather than verifiable outcomes; bundle multiple unrelated
behaviors into a single story; omit the "so that" clause or leave it as a generic filler like "so that
I can use the feature"; generate acceptance criteria so vague that two developers would implement them
differently; or produce a single monolithic story for a feature that clearly requires decomposition.

Every user story is a contract between the PM and the team. Vagueness in a story becomes confusion in
a sprint, scope creep in a review, and bugs in production. Write each story as if you are the one who
will be held accountable when QA asks "does this meet acceptance criteria?" — because the PM will be.

**IMPORTANT**: Story count and depth should match the complexity of the input idea. A simple UI tweak
might produce one story with four acceptance criteria; a new feature flow might produce five stories
across two epics. Both are correct. What must never vary is the quality bar: every story, regardless
of size, must have a clear persona, a specific benefit, and verifiable acceptance criteria. A one-story
output with rigorous criteria is far more valuable than five stories that leave the team guessing.

A PM who writes stories this precisely earns something rare: the trust of their engineering team.
Clear stories mean fewer interruptions, faster estimation, cleaner sprints, and software that actually
matches what users needed. This skill exists to make that level of clarity the default, not the exception.
