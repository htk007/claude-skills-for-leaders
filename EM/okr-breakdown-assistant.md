---
name: okr-breakdown-assistant
description: "Use this skill when an Engineering Manager needs to translate high-level team or company goals into structured OKRs. Triggers: any request involving writing key results for a given objective, turning vague goals into measurable outcomes, pressure-testing whether OKRs are actually measurable, aligning team OKRs to company-level objectives, or splitting an objective into initiatives. Also use when the EM wants to sanity-check OKRs they've already drafted for clarity, ambition, or measurability. Do NOT use for personal development goals, performance reviews, or sprint planning."
---

# OKR Breakdown Assistant

## Overview

Translating team goals into good OKRs is harder than it looks. A well-formed OKR needs to be:
- **Outcome-focused** — key results measure impact, not activity
- **Measurable** — a number, a threshold, or a clear binary outcome
- **Ambitious but honest** — stretch goals that the team can actually influence
- **Aligned** — traceable back to a company or org-level objective

This skill turns your rough goal statements into structured, pressure-tested OKRs — with key results your team can actually track.

---

## What This Skill Does

Given your objective and context, it generates:

1. A **refined objective** (clear, outcome-oriented, time-bound)
2. **3–4 key results** (measurable, with target values and baseline where possible)
3. A **risk flag** for each KR (what could make it misleading or gameable)

---

## Key Result Quality Levels

| Level | Label | What It Means |
|-------|-------|---------------|
| ✅ | `[STRONG]` | Measurable, outcome-focused, hard to game |
| 🟡 | `[WEAK]` | Too vague, output-focused, or missing a target value |
| 🔴 | `[REWRITE]` | Activity metric disguised as a result — needs a full rethink |
| 💡 | `[ALTERNATIVE]` | A suggested replacement or companion KR |

---

## How to Use

Paste your goal and context in this format:

```
OBJECTIVE: [Your rough goal statement — can be messy or high-level]
TEAM: [e.g., Platform, Mobile, Data, Full-stack product team]
TIMEFRAME: [e.g., Q3 2025, H2 2025]
COMPANY GOAL: [Optional — the org or company objective this should ladder up to]

DRAFT KRs:
[Optional — paste any key results you've already drafted, even rough ones]

CONTEXT:
[Optional — current baseline metrics, known constraints, team size, past OKR performance]
```

Claude will output a structured, ready-to-use OKR set.

---

## Example Input

```
OBJECTIVE: Make our platform more reliable
TEAM: Platform Engineering (6 engineers)
TIMEFRAME: Q3 2025
COMPANY GOAL: Become the most trusted infrastructure provider for internal teams

DRAFT KRs:
- Improve uptime
- Reduce incidents
- Engineers are happier with the platform

CONTEXT:
Current p99 latency is 420ms. We had 4 SEV-2 incidents last quarter. Internal NPS from
engineering teams is around 32. We've never formally tracked MTTR.
```

## Example Output

---

**🎯 OKR — Platform Engineering | Q3 2025**

---

**Objective (refined)**

> *Make the platform the most reliable foundation internal engineering teams have ever shipped on.*

This tightens the original — it's time-bound by the quarter, outcome-oriented, and ties directly to the company goal of internal trust.

---

**KR 1 — Uptime & Latency**

> Reduce p99 API latency from 420ms to under 250ms, measured across all internal consumers.

✅ `[STRONG]` — Specific, directional, anchored to a real baseline. Hard to game because it covers all consumers, not a cherry-picked endpoint.

⚠️ *Risk:* If the team optimizes only the most-used endpoint, the metric could hit target while tail latency stays broken. Consider adding a "no single endpoint excluded" qualifier if this is a risk in practice.

---

**KR 2 — Incident Reduction**

> Reduce SEV-2 or higher incidents from 4 to 1 per quarter, with MTTR under 45 minutes for any that occur.

✅ `[STRONG]` — Two sub-metrics that work together: frequency and recovery speed. Prevents gaming (you can't just reclassify incidents as SEV-3).

⚠️ *Risk:* Incident counts can fluctuate due to factors outside the team's control (e.g., traffic spikes, upstream changes). Flag this as a leading indicator of reliability work, not a pure performance judgment.

---

**KR 3 — Internal Engineering Satisfaction**

> Increase internal platform NPS from 32 to 50, based on end-of-quarter survey with at least 70% response rate.

🟡 `[WEAK]` as originally stated ("engineers are happier") — rewritten above to include a baseline, a target, and a response rate floor.

⚠️ *Risk:* NPS can be influenced by factors beyond platform quality (team dynamics, workload). Use it as a signal, not a verdict.

💡 `[ALTERNATIVE]` — If NPS feels too soft, consider: *"Reduce the number of platform-related support requests per team per month from X to Y"* — more directly tied to reliability perception.

---

**KR 4 — Operational Maturity (suggested addition)**

> Establish MTTR baseline by week 2 of Q3 and publish a weekly reliability dashboard visible to all engineering teams by end of Q3.

🔵 *This is a process KR, not an outcome KR — but it's worth including for Q3 specifically because you're starting from zero visibility. Treat it as a foundation KR that enables future quarters to be fully outcome-based.*

---

**⚠️ Overall Risk Flags**

- KR 1 and KR 2 are strong but the team should own the measurement method upfront — agree on how latency and incidents are counted before the quarter starts, not at the end
- Avoid stacking all KRs on metrics the team has never tracked before — at least one KR should have historical data behind it

---

## Variations

**"Just pressure-test my existing OKRs"**
→ Ask: *"Review these KRs for measurability, gaming risk, and alignment. Don't rewrite unless needed."*

**"I need to align this to a company objective"**
→ Include the COMPANY GOAL field — Claude will explicitly map each KR to it

**"Our OKRs need to be more ambitious"**
→ Ask: *"Rewrite these KRs assuming the team performs in the top quartile. What would stretch look like?"*

**"I need to explain these OKRs to my team"**
→ Ask: *"Write a short narrative (5–6 sentences) I can read at the start of our Q3 kickoff to explain why these OKRs matter."*

---

## Tips for Best Results

- Always include your current baseline — without it, Claude will flag KRs as weak even if they're directionally right
- Paste your draft KRs even if they're rough — it's faster to pressure-test and improve than to start from zero
- If your objective sounds like a project ("launch the new observability stack"), Claude will help reframe it as an outcome
- One activity KR per quarter is fine — just label it as such so the team knows it's a means, not an end
