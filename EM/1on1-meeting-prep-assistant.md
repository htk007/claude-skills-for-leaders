---
name: 1on1-meeting-prep-assistant
description: "Use this skill when an Engineering Manager needs to prepare for a 1:1 meeting with a direct report. Triggers: any request involving planning a 1:1 agenda, turning scattered notes into structured meeting topics, deciding what to bring up in a 1:1, preparing follow-up questions from a previous meeting, or figuring out how to open a difficult conversation in a 1:1 context. Also use when the EM wants to make the meeting more focused, balanced, or productive. Do NOT use for team meetings, performance reviews, or incident retrospectives."
---

# 1:1 Meeting Prep Assistant

## Overview

A good 1:1 is the most valuable recurring meeting on your calendar. But it's easy to walk in underprepared — or to let it turn into a status update. A well-prepped 1:1 needs to be:
- **Focused** — 2–3 real topics, not a laundry list
- **Two-directional** — space for what the engineer wants to bring, not just the EM
- **Contextual** — aware of what was said last time and what's changed since
- **Honest** — the right place to raise hard things before they become big things

This skill turns your scattered notes, open threads, and gut feelings into a structured 1:1 agenda — with suggested questions for each topic.

---

## What This Skill Does

Given your context and rough notes, it generates:

1. A **prioritized agenda** (2–4 topics with suggested questions)
2. A **suggested opening** (tone-calibrated to the situation)
3. A **carry-forward note** (what to track for next time)

---

## Meeting Modes

| Mode | Label | When to Use |
|------|-------|-------------|
| 🟢 | `[REGULAR]` | Routine weekly or biweekly check-in |
| 🟡 | `[SIGNAL]` | Something feels off — performance, morale, or engagement |
| 🔴 | `[CRITICAL]` | Difficult conversation: underperformance, conflict, or a big career moment |
| 🔵 | `[GROWTH]` | Focus on development, promotion path, or career goals |

---

## How to Use

Paste your context and notes in this format:

```
ENGINEER: [Name or alias]
LEVEL: [e.g., Junior, Mid, Senior, Staff — or leave blank]
LAST MET: [e.g., "2 weeks ago" or leave blank]
MODE: [REGULAR / SIGNAL / CRITICAL / GROWTH]

OPEN THREADS:
[Anything unresolved from last time — promises made, topics deferred, feedback given]

MY NOTES:
[Your raw observations since the last 1:1 — incidents, wins, concerns, peer mentions,
your gut feeling. Bullet points, messy notes, Slack screenshots — anything goes.]

ENGINEER'S LIKELY TOPICS:
[Optional — what you expect them to bring up, if you know]
```

Claude will output a focused, ready-to-use 1:1 agenda.

---

## Example Input

```
ENGINEER: Lena
LEVEL: Mid
LAST MET: 10 days ago
MODE: SIGNAL

OPEN THREADS:
- I said I'd follow up on whether she could lead the onboarding revamp project
- She mentioned feeling "a bit stuck" last time — I didn't have time to dig into it

MY NOTES:
- Delivery has been fine but she's been quiet in team meetings lately
- Pulled her into a production incident last week — she handled it well under pressure
- Heard from another engineer that she's been frustrated about the direction of the product
- She hasn't taken on anything new in 6 weeks

ENGINEER'S LIKELY TOPICS:
- Probably the onboarding project decision
- Maybe the product direction thing
```

## Example Output

---

**📋 1:1 Agenda — Lena | Mid Engineer**
*Mode: 🟡 SIGNAL — something to pay attention to*

---

**🟡 [SIGNAL] — Opening**

Don't open with the agenda. Start with something genuine:

> *"Before we get into things — how are you actually doing? Last time you mentioned feeling a bit stuck and I want to make sure we get back to that."*

This signals that you remembered and that the 1:1 is her space, not just yours.

---

**Topic 1 — The "stuck" thread (carry-forward)**

This was left open last time. It's the most important thing on this agenda.

Suggested questions:
- *"Last time you said you were feeling stuck — can you say more about that? Is it the work itself, the team, the direction?"*
- *"Is there something you wish you were doing that you're not?"*
- *"On a scale of 1–10, how energized do you feel about your work right now?"*

Listen more than you talk here. The goal is to understand what's underneath, not to fix it immediately.

---

**Topic 2 — Onboarding revamp decision (open thread)**

You owe her an answer. Come in prepared with one.

If yes: frame it as a real opportunity with clear scope and support.
If not yet: be honest about why, and give her a timeline.

Suggested questions:
- *"I've been thinking about the onboarding revamp — I want to share where I landed and get your reaction."*
- *"If you were to take this on, what would you need from me to feel set up for success?"*

---

**Topic 3 — Product direction frustration (signal from peer)**

You heard something secondhand. Don't ambush her with it — open a door instead.

Suggested questions:
- *"I've been curious — what's your honest read on the direction we're heading as a team?"*
- *"Is there anything about the product decisions lately that's been hard to get behind?"*

If she brings it up herself: validate the concern, share your perspective, and be honest about what's in your control vs. not.

---

**🔵 Carry-Forward — Track for Next Time**

- [ ] Did she open up about what "stuck" means? What did you learn?
- [ ] Onboarding project: decision communicated, reaction noted
- [ ] Product frustration: surface-level or something deeper?
- [ ] Has engagement in team meetings changed by next session?

---

## Variations

**"I just need a quick agenda, nothing deep"**
→ Ask: *"Give me a 3-bullet agenda only, no questions"*

**"I need to open a difficult conversation"**
→ Set MODE to `CRITICAL` and describe the situation in MY NOTES

**"I want to focus on their career growth"**
→ Set MODE to `GROWTH` and include what you know about their goals

**"I have almost no notes — we've been heads-down"**
→ Ask: *"I have nothing specific to bring. Generate a general check-in agenda for a [junior/senior] engineer."*

---

## Tips for Best Results

- The "stuck" signals matter most — if something feels off, name it in MY NOTES even if it's vague
- Always include open threads from last time — the fastest way to erode trust is forgetting what you promised
- Mode changes the entire output: SIGNAL and CRITICAL give you more coaching language, REGULAR keeps it lightweight
- You don't have to follow the agenda exactly — it's a thinking tool, not a script
