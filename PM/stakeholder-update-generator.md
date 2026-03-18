---
name: stakeholder-update-generator
description: >
  Use this skill whenever a Product Manager needs to transform raw progress notes, bullet points, or
  informal updates into a polished stakeholder communication. Triggers include: phrases like "write a
  stakeholder update", "turn these notes into an update", "draft a status update for leadership",
  "polish this progress summary", "write an exec update", "format this for stakeholders", "I need to
  send an update to the steering committee", or any request where the user has rough notes, a brain dump,
  or a list of progress points and wants them shaped into a professional, audience-calibrated communication.
  Also trigger when the user describes what happened in a sprint, a project phase, or a milestone week
  and wants it formatted for a non-technical or senior audience. If the input contains progress
  information of any kind — risks, decisions, blockers, milestones, metrics — default to producing a
  stakeholder update rather than asking for more structure first. Raw input is the expected starting
  point; shaping it is the skill's job.
---

Produces a polished, audience-calibrated stakeholder update from raw progress notes — with the right
tone, the right level of detail, and a clear signal-to-noise ratio that respects senior stakeholders'
time while keeping them genuinely informed and appropriately alerted to risks.

The user provides **raw progress material**: bullet points, sprint notes, a brain dump, a Slack thread
summary, a list of completed items and blockers, or a rough paragraph written under time pressure. They
may also specify the audience (exec team, steering committee, external partner, board) and the format
(email, Slack, weekly digest, slide narrative). The skill shapes whatever is given into a communication
that sounds like a confident, prepared PM — not a rushed one.

## Thinking Process

Before drafting the update, understand the audience and commit to a clear editorial frame:

- **Purpose**: A stakeholder update exists to maintain trust and informed alignment — not to report
  activity. The difference matters. Activity reporting says "we completed 14 tickets this sprint."
  Aligned stakeholder communication says "we are on track to deliver the checkout redesign by March 14,
  the one remaining risk is the third-party payment API dependency, and here is what we are doing about
  it." Stakeholders do not need to know what the team did; they need to know whether the initiative is
  on track, what decisions or support are needed from them, and whether any risks require their attention.
- **Tone/Approach**: Calibrate tone precisely to the audience. Executive and board-level updates:
  confident, concise, outcome-oriented, no jargon. Steering committee updates: structured, metric-aware,
  risk-transparent. External partner updates: professional, relationship-conscious, selectively detailed.
  Internal team-adjacent updates: direct, slightly more technical. In all cases: no hedging, no
  over-explanation, no burying of bad news under good news. Respect for the reader's time is the
  baseline; earning their trust is the goal.
- **Constraints**: The update must be readable in under three minutes at the level of detail provided.
  Risks and blockers must appear prominently — never at the end, never softened to the point of
  invisibility. Decisions required from stakeholders must be explicit asks, not implied. The update
  should not require the reader to remember context from previous communications — it should be
  self-contained enough to stand alone.
- **Differentiation**: A generic status update reformats bullet points into prose. A great stakeholder
  update makes editorial choices: what to lead with, what to consolidate, what to flag, what to omit.
  It translates team-level activity into business-level meaning. It treats the stakeholder as a
  decision-maker, not an auditor. And it anticipates the three questions every stakeholder silently
  asks when reading: Are we on track? Are there risks I should know about? Is there anything you need
  from me?

**CRITICAL**: The PM's credibility with senior stakeholders is built or eroded one update at a time.
An update that buries a risk, overloads with detail, or reads like a task list trains stakeholders
to skim — and to lose confidence in the PM's judgment. An update that is precise, honest, and
structured for the reader's needs trains stakeholders to trust the PM's signal. Every update produced
by this skill must answer the three silent questions — on track / risks / asks — clearly and early,
and must make the PM sound like someone who is in control of the narrative, not just reporting it.

Then produce a **stakeholder update document** (in the format most appropriate to the context —
email, Slack-length summary, structured digest, or narrative memo) that is:
- Scannable in under three minutes by a senior stakeholder with no prior context for this update
- Honest about risks and blockers — named early, not minimized or buried
- Action-oriented — any decisions or support needed from the reader are explicit and specific
- Calibrated to the audience — the right depth, the right vocabulary, the right level of confidence

---

## Stakeholder Update Writing Guidelines

Focus on:

- **Audience Calibration**: Before writing a single sentence, identify the audience tier and adjust
  accordingly. C-suite and board: lead with business outcome and status, one paragraph maximum per
  topic, no sprint terminology or technical detail unless directly relevant to a risk. Steering
  committee or VP level: structured sections, metrics included, risks with mitigation context.
  Cross-functional peers: direct and peer-level, more operational detail acceptable. External partners:
  relationship-aware, selective, professionally warm. If the user does not specify the audience,
  default to executive-level calibration — it is easier to add detail than to remove it after sending.

- **Status Signal First**: Open with the headline status — a single clear signal of where the
  initiative stands. Use a simple RAG (Red / Amber / Green) label or equivalent plain-language
  equivalent ("on track", "at risk", "off track") followed by one sentence of context. Do not make
  the reader infer the status from the body of the update. Do not open with accomplishments if there
  is a meaningful risk — lead with the risk. Stakeholders who discover a buried risk after reading
  three paragraphs of good news lose trust in the PM's judgment faster than they lose trust in the
  project's health.

- **Progress Summary**: Summarize what was completed or advanced since the last update — but frame
  completions as progress toward the goal, not as a task list. "The authentication module is complete
  and integrated; we are now three weeks from feature-complete on the MVP" is stakeholder language.
  "We finished 11 of 14 planned tickets and merged 23 PRs" is team-internal language. Translate
  relentlessly. Consolidate related items; do not itemize every sub-task. Three to five meaningful
  progress points are almost always the right number regardless of how much was actually done.

- **Risks, Blockers & Decisions Required**: This section must appear in every update, even if the
  content is "no current blockers." Stakeholders who never see a risk section learn to assume updates
  are sanitized — and stop trusting them. For each risk or blocker: name it plainly, state the
  potential impact on timeline or outcome, describe what is being done to mitigate it, and identify
  whether stakeholder action or awareness is needed. Format decisions required as explicit asks:
  "We need a decision on X by [date] to avoid impacting the Y milestone." Never imply; always state.

- **What's Next**: Close the body of the update with a brief forward-looking paragraph — the two or
  three most important things happening before the next update. This orients the reader toward the
  next checkpoint and implicitly signals that the PM has a plan. Keep it to three items maximum;
  a long "next steps" list signals lack of prioritization. If a key milestone or decision point is
  approaching, name it with a date.

- **Format Discipline**: Match the format to the channel. Email: subject line that signals status
  ("Project X — On Track | Week 12 Update"), clear section headers, no more than 300–400 words for
  a routine update. Slack or async digest: shorter, punchier, use bold for the status signal and
  asks. Narrative memo or steering committee doc: structured with headers, metrics table if relevant,
  risk section with more depth. In all formats: no walls of prose, no orphaned bullet points without
  context, no closing pleasantries that delay the reader from acting.

NEVER produce a stakeholder update that: opens with a list of completed tasks before stating the
overall status; buries a risk or blocker in the middle or end of the update; uses team-internal
jargon (sprint velocity, story points, ticket counts) without translation for a non-technical
audience; writes "no blockers" when there are known risks that don't yet have a mitigation plan;
makes a decision request implicit rather than explicit; or pads the update with context the audience
already has in order to appear thorough.

A stakeholder update is not a report — it is a managed communication. The PM decides what the
stakeholder needs to know, in what order, and at what level of detail. That editorial judgment is
not spin; it is the PM's core responsibility. Own it.

**IMPORTANT**: Update length must match the audience and cadence. A weekly executive Slack update
may be five sentences. A monthly steering committee memo may run two pages with a metrics table.
Both are correct for their context. What must never vary is structural integrity: every update,
regardless of length or format, must contain a clear status signal, honest risk disclosure, and
explicit asks if any exist. An update that omits any of these three elements — regardless of how
polished the prose is — has failed its primary purpose.

A PM who communicates with this level of precision and audience awareness builds something that
cannot be manufactured any other way: a reputation for reliable signal. When that PM sends an
update, stakeholders read it. When that PM flags a risk, stakeholders act on it. When that PM says
the initiative is on track, stakeholders believe it. That reputation is built one well-crafted
update at a time — and this skill exists to make every one of them count.
