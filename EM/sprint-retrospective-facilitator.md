---
name: sprint-retrospective-facilitator
description: >
  Use this skill whenever an Engineering Manager needs to structure sprint retrospective outcomes into
  a clear, actionable team summary. Triggers include: phrases like "write up our retro", "summarize
  the retrospective", "turn these retro notes into action items", "structure our sprint retrospective",
  "we finished our retro and need a summary", "format our retrospective outcomes", "create retro action
  items", or any request where the user provides raw retrospective input — sticky notes, bullet points,
  a list of what went well / what didn't, team feedback, or meeting notes — and wants it shaped into
  a structured, shareable team document. Also trigger when the EM wants to draft a retro summary from
  memory, a partial set of notes, or a rough dump of team sentiment. If the input touches team process,
  sprint health, or recurring friction — however unstructured — default to producing a retrospective
  summary rather than asking for a cleaner input first.
license: Complete terms in LICENSE.txt
---

Produces a structured, actionable sprint retrospective summary from raw retro inputs — transforming
team feedback, observations, and discussion outcomes into a shareable document with clear action items,
owners, and follow-through hooks that make the retro count beyond the meeting room.

The user provides **retrospective raw material**: this can range from sticky note exports, a bulleted
brain dump of what the team discussed, a "went well / didn't go well / try next sprint" list, a Miro
or FigJam board export, or a rough summary written from memory. The skill shapes whatever is given
into a complete retro summary ready to be shared with the team and tracked across future sprints.

## Thinking Process

Before structuring the retro summary, understand the team context and commit to a clear framing:

- **Purpose**: A retro summary exists to make the retrospective durable — transforming a one-hour
  conversation into a written record that the team can reference, act on, and measure against in
  the next sprint. The EM's job is not to moderate the meeting; it is to ensure the outcomes of that
  meeting produce real change. A retro with no written follow-through is a venting session. A retro
  with a clear, owned action list is a process improvement engine.
- **Tone/Approach**: Honest, neutral, and team-centered. The summary should reflect the team's voice,
  not reframe or soften what was said. Friction points must be named clearly — not euphemized into
  "areas for growth." At the same time, the tone must remain constructive: the goal is forward motion,
  not a post-mortem audit. Write as if the EM respects the team enough to tell the truth and trusts
  them enough to act on it.
- **Constraints**: Action items must be specific, owned, and time-bound — not aspirational statements.
  The summary must be scannable in under two minutes. It should be shareable as-is to the full team,
  to the EM's manager, or to a new team member joining next sprint. Sensitive interpersonal dynamics
  should be noted carefully — surfaced where relevant to process, anonymized where personal.
- **Differentiation**: Generic retro summaries list what was said. A great retro summary identifies
  patterns across feedback, connects recurring themes to systemic causes, separates one-time noise
  from structural friction, and produces action items that address root causes rather than symptoms.
  It also preserves the team's wins explicitly — not as filler, but as evidence of what to protect
  and repeat.

**CRITICAL**: The retrospective summary is one of the highest-leverage documents an EM produces
regularly. Teams that feel their retro feedback disappears into a document no one reads will stop
giving honest feedback. Teams that see their feedback turn into named actions with visible follow-through
develop a culture of continuous improvement. Every summary produced by this skill must be specific
enough that the team can hold itself accountable to it — and the EM can open it at the start of the
next retro and say "here is what we committed to, here is what happened."

Then produce a **Markdown retrospective summary document** that is:
- Immediately shareable to the team without editing or redaction
- Specific enough for every action item to be tracked in a ticket or next-sprint commitment
- Balanced — wins documented with the same rigor as friction points
- Forward-looking — past observations converted into future commitments, not just complaints on record

---

## Retrospective Summary Writing Guidelines

Focus on:

- **Sprint Snapshot**: Open with a one-paragraph sprint summary — the sprint goal, whether it was
  met, the team's overall sentiment, and the headline story of the sprint (what defined it, positively
  or negatively). This gives anyone reading the document — including the team in six months — immediate
  context without needing to remember the sprint. Include: sprint number or date range, team name or
  squad if relevant, and participation note (e.g., "7 of 8 team members present").

- **What Went Well**: Document genuine wins with specificity. Not "good collaboration" but "the
  pairing sessions between frontend and backend on the auth flow unblocked three tickets that had
  been stalled for two sprints." Group related wins into themes if the list is long. Flag wins that
  should be institutionalized — practices worth protecting, formalizing, or scaling to other teams.
  Wins that are named are wins that are repeated; wins that are vague are wins that disappear.

- **What Didn't Go Well**: Name friction, blockers, and failures directly. Organize by theme where
  patterns exist (e.g., "Estimation accuracy", "Cross-team dependencies", "Definition of Done gaps").
  For each theme, capture: what happened, how often or how severely it affected the sprint, and
  whether this is a recurring pattern or a one-time occurrence. Do not soften recurring systemic
  issues into polite observations — if the team has raised the same friction three sprints in a row,
  name it as a pattern and escalate its priority in the action items accordingly.

- **Action Items**: This is the most important section. Every action item must have: a clear description
  of what will be done (not "improve communication" but "add a 10-minute async standup blocker update
  to Slack by 9am daily, trialed for two sprints"), a named owner (a person, not a role), a target
  completion date or sprint, and a success indicator (how will the team know this action had the
  intended effect). Categorize as: Process changes, Tooling or workflow improvements, Team agreements,
  or Escalations to leadership or other teams. Flag which items are carryovers from previous retros —
  recurring action items that haven't landed are a signal the root cause hasn't been addressed.

- **Patterns & EM Observations**: Include a brief section of EM-level synthesis — observations the
  team may not have named explicitly but that emerge from the pattern of feedback. This is where the
  EM adds value beyond facilitation: connecting this sprint's retro to previous ones, flagging team
  health signals (energy, psychological safety, sustainable pace), and noting anything that requires
  escalation or structural intervention beyond the team's own control. Write this section in first
  person as the EM's voice — it is not a neutral summary but an informed perspective.

- **Follow-Through Hook**: Close with a concrete commitment to accountability. State how action items
  will be tracked (Jira, Notion, retro board, etc.), when the EM will check in on progress, and how
  the next retro will open — explicitly reviewing whether this sprint's action items were completed.
  A retro without a follow-through hook produces learned helplessness; a retro that opens with
  "last sprint we committed to X — let's check" builds a culture of accountability.

NEVER produce a retro summary that: lists action items without owners or deadlines; uses passive voice
to describe friction ("there were some communication challenges") when active framing is possible
("the team did not have a shared agreement on PR review SLAs, causing three tickets to miss the sprint
due to review delays"); treats all feedback as equally weighted regardless of frequency or impact;
omits the wins section or treats it as a formality; produces action items that address symptoms rather
than causes; or softens recurring systemic issues to avoid discomfort.

Every retro summary is a mirror the team holds up to itself. The EM's job is to make sure the
reflection is accurate — honest about what is broken, generous about what is working, and precise
about what will change. A summary that makes everyone comfortable has probably not told the whole
truth. A summary that makes the team feel seen, heard, and equipped to improve has done its job.

**IMPORTANT**: Summary length should match retro complexity and team size. A small team with a
straightforward sprint may need a single page; a larger team with multiple workstreams and recurring
friction may need structured sub-sections and a longer action item table. Both are valid. What must
never vary is structural completeness: every summary, regardless of length, must contain a sprint
snapshot, wins, friction points, owned action items, and a follow-through hook. A short summary that
covers all five dimensions honestly is always more valuable than a long summary that pads the wins
section and buries the action items at the end.

An EM who runs retros at this standard builds something rare: a team that believes improvement is
possible, that their feedback matters, and that the process works in their favor. That belief is not
built in a single retrospective — it is built sprint by sprint, summary by summary, action item by
action item. This skill exists to make that standard achievable every time.
