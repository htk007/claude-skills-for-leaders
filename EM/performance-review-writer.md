---
name: performance-review-writer
description: "Use this skill when an Engineering Manager needs to write a performance review. Triggers: any request involving turning manager notes into a structured review, writing quarterly or annual performance evaluations, drafting growth-oriented feedback for engineers, converting rough observations into professional review language, or preparing promotion packet narratives. Also use when the manager wants to make feedback more balanced, evidence-based, or bias-free. Do NOT use for real-time feedback after a single incident, disciplinary documentation, or compensation decision memos."
---

# Performance Review Writer

## Overview

Writing performance reviews is one of the highest-leverage — and most time-consuming — responsibilities of an Engineering Manager. A good review needs to be:
- **Evidence-based** — every claim anchored to specific behavior or outcomes
- **Balanced** — honest about both strengths and growth areas, without softening either
- **Fair** — free from recency bias, halo effect, and gender-coded language
- **Growth-oriented** — ends with a clear, actionable development path

This skill turns your raw notes into structured, professional performance reviews — ready to paste into your HR system or share directly with the engineer.

---

## What This Skill Does

Given your unstructured notes and context, it generates:

1. A **per-section review** (Impact, Technical Excellence, Collaboration)
2. **Growth areas** with specific, actionable expectations
3. A **closing summary** (calibrated to rating and seniority)

---

## Review Structure Used

| Section | What It Covers |
|--------|----------------|
| 📦 Impact & Delivery | Project outcomes, ownership, deadline behavior |
| 🔧 Technical Excellence | Code quality, architecture judgment, communication of technical decisions |
| 🤝 Collaboration & Influence | Peer feedback, mentorship, handling disagreement |
| 🚀 Growth Focus Areas | 2–3 concrete, named expectations for the next cycle |
| ✅ Closing Summary | Overall narrative tied to rating and trajectory |

---

## How to Use

Paste your notes in this format:

```
NAME: [Engineer's name or alias]
LEVEL: [e.g., L3, Mid, Senior, Staff — or leave blank]
PERIOD: [e.g., H1 2025, Q1–Q2, last 6 months]
RATING: [e.g., Meets Expectations, Exceeds, Needs Improvement — or leave blank]

NOTES:
[Paste your raw notes here — bullet points, Slack messages, project names,
peer feedback quotes, your own observations. No formatting required.]
```

Claude will output a structured, ready-to-submit performance review.

---

## Example Input

```
NAME: Deniz
LEVEL: Senior Engineer
PERIOD: H1 2025
RATING: Exceeds Expectations

NOTES:
- Led the migration of our auth service to the new identity provider. Took 3 months, basically zero incidents.
- Stepped up when the team lead was on parental leave — ran standups, unblocked people, didn't complain.
- Peer feedback from Amara: "Deniz always makes time to explain things. Never makes you feel dumb for asking."
- Sometimes goes too deep on technical details in design docs — loses non-eng stakeholders.
- Missed the billing integration deadline by 2 weeks. Scope crept but didn't flag it early enough.
- Started mentoring two junior engineers this cycle — both seem to really value it.
- Gets frustrated when architecture decisions go a different way. A couple of tense moments in design reviews.
```

## Example Output

---

**Performance Review — Deniz | Senior Engineer | H1 2025**
*Rating: Exceeds Expectations*

---

**📦 Impact & Delivery**

Deniz delivered one of the most technically complex projects of the half: a full migration of the auth service to the new identity provider. The project spanned three months, involved significant cross-team coordination, and shipped with zero production incidents — a strong signal of both technical rigor and disciplined execution.

When the team lead went on parental leave mid-cycle, Deniz absorbed coordination responsibilities without being asked. Standups ran smoothly, blockers were resolved, and team velocity held. This kind of ownership — stepping into a gap without formal authority — reflects the instincts of someone operating above their current level.

One area to develop: deadline risk signaling. The billing integration shipped two weeks late due to scope expansion that was visible earlier in the cycle. The scope concern was legitimate; surfacing it sooner would have enabled earlier replanning. The expectation going forward is a proactive flag when timeline or scope assumptions shift — not after a slip has already occurred.

---

**🔧 Technical Excellence**

Deniz brings deep technical judgment to the team and consistently produces high-quality architecture proposals. This is a genuine strength others rely on.

The growth edge is audience calibration in written communication. Several design documents this cycle went deep on implementation detail in ways that lost non-engineering stakeholders. The technical substance was sound; the framing needs to flex. For H2: when writing for mixed audiences, lead with the decision and the tradeoffs, and reserve implementation detail for an appendix.

---

**🤝 Collaboration & Influence**

Peer feedback consistently highlights Deniz's accessibility and patience. Amara noted that Deniz creates space for questions without judgment — a quality with real impact on psychological safety, especially for junior teammates.

Deniz also took on mentorship of two junior engineers this cycle, an investment that goes beyond Senior-level expectations and signals emerging leadership potential.

One area to work on: receiving decisions that go against a stated technical position. Deniz has strong opinions — which is valuable — but a few design review moments became tense when the outcome didn't align with the recommendation. The goal isn't less conviction; it's separating advocacy from acceptance. Disagreeing and committing visibly builds the credibility that makes future technical influence more effective.

---

**🚀 Growth Focus Areas — H2 2025**

1. **Stakeholder-calibrated communication** — Lead with the decision and tradeoffs in documents that cross engineering boundaries; move implementation detail to appendices.
2. **Early risk signaling** — Flag scope or timeline uncertainty at the moment it's identified, not after it has materialized.
3. **Graceful disagreement** — Commit publicly and constructively when a decision goes another way, even when you'd have chosen differently.

---

**✅ Closing Summary**

Deniz had an exceptional first half. The auth migration alone would have made this a strong cycle; the leadership coverage during parental leave elevated it further. The development areas are real and worth taking seriously — but they are the growing edges of a Senior engineer on a clear path toward Staff-level contribution.

---

## Variations

**"My company uses a different review template"**
→ Ask: *"Adapt the output to this structure: [paste your template sections]"*

**"I've already drafted something — check it for bias"**
→ Ask: *"Review this draft for recency bias, halo effect, and gender-coded language. Flag issues and suggest rewrites."*

**"I don't have many notes"**
→ Ask: *"I have limited notes. Ask me questions before drafting."*

**"This is an underperformance situation"**
→ Add to your input: *"This review involves underperformance. Be direct, avoid language that softens the severity, and include clear expectations for the next cycle."*

**"This review will accompany a promotion case"**
→ Add to your input: *"This is a promotion packet for [target level]. Emphasize scope expansion, influence beyond the team, and evidence of operating above current level."*

---

## Tips for Best Results

- The messier your notes, the better — don't clean them up before pasting
- Include peer feedback verbatim when you have it — Claude will synthesize it appropriately
- Always specify the level — it changes what "exceeds expectations" means and how growth areas are framed
- For promotion packets, mention the target level explicitly
- You can paste Slack messages, 1:1 notes, or incident summaries directly into the NOTES field
