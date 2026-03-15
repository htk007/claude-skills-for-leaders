# Performance Review Writer

## Description
Turn raw manager notes, Slack highlights, peer feedback snippets, and project outcomes into structured, fair, and growth-oriented performance reviews — ready to paste into your HR system or share directly with the engineer.

## Overview
Writing performance reviews is one of the highest-leverage — and most time-consuming — responsibilities of an Engineering Manager. Done well, reviews accelerate careers, build trust, and document impact. Done poorly, they feel generic, biased toward recency, or vague.

This skill takes your unstructured notes and transforms them into a balanced, evidence-based review that:
- Anchors every claim to specific, observable behavior or outcomes
- Covers both strengths and areas for growth without softening either
- Uses language that is fair, direct, and free of common bias patterns (recency bias, halo effect, gender-coded language)
- Ends with a clear, actionable development path

**Target role:** Engineering Manager (EM)
**Typical use:** Quarterly or annual performance cycles, mid-year check-ins, PIP documentation, promotion packets

---

## Input Format

Paste your raw notes inside `<review_input>` tags. Include as much or as little as you have — the skill works with messy, incomplete input.

```
<review_input>
name: [Engineer's name or alias]
level: [e.g., L3, Senior, Staff — or leave blank]
review_period: [e.g., Q1–Q2 2025, or "last 6 months"]
rating_if_known: [e.g., Meets Expectations, Exceeds, or leave blank]

notes:
[Paste your raw notes here — bullet points, Slack messages, project names,
peer feedback quotes, your own observations. No formatting required.]
</review_input>
```

---

## Example Input

```
<review_input>
name: Deniz
level: Senior Engineer
review_period: H1 2025
rating_if_known: Exceeds Expectations

notes:
- Led the migration of our auth service to the new identity provider. It was a huge project, took 3 months, basically zero incidents.
- Really stepped up when the team lead was on parental leave — ran standups, unblocked people, didn't complain once.
- Peer feedback from Amara: "Deniz always makes time to explain things. Never makes you feel dumb for asking."
- Sometimes goes too deep on technical details in design docs — loses the audience when writing for non-eng stakeholders.
- Missed the first deadline on the billing integration by 2 weeks. Said it was scope creep. Probably true but didn't flag it early enough.
- Started mentoring two junior engineers this cycle — both seem to really value it.
- Strong opinions about architecture. Gets frustrated when decisions go a different way. Couple of tense moments in design reviews.
</review_input>
```

---

## Example Output

---

**Performance Review — Deniz | Senior Engineer | H1 2025**
*Rating: Exceeds Expectations*

---

### Impact & Delivery

Deniz delivered one of the most technically complex projects of the half: a full migration of the auth service to the new identity provider. The project spanned three months, involved significant coordination across teams, and shipped with zero production incidents — a strong indicator of both technical rigor and careful execution.

When the team lead went on parental leave mid-cycle, Deniz absorbed team coordination responsibilities without being asked. Standups ran smoothly, blockers were resolved, and team velocity was maintained. This kind of ownership — stepping into a gap without formal authority — reflects the instincts of someone operating above their current level.

One area to develop: deadline risk signaling. The billing integration shipped two weeks late due to scope expansion that, in retrospect, was visible earlier in the cycle. The scope concern was legitimate, but surfacing it sooner would have enabled earlier re-planning. Going forward, the expectation is a proactive flag when scope or timeline assumptions shift — not after the slip has occurred.

---

### Technical Excellence

Deniz brings deep technical judgment to the team and consistently produces high-quality architecture proposals. This is a genuine strength and one others rely on.

The growth edge here is audience calibration in written communication. Several design documents this cycle went deep on implementation detail in ways that lost non-engineering stakeholders. The technical substance was sound; the framing needs to flex. The ask for H2: when writing for a mixed audience, lead with the decision and the tradeoffs, and reserve implementation detail for an appendix or follow-up.

---

### Collaboration & Influence

Peer feedback consistently highlights Deniz's accessibility and patience. Amara noted that Deniz creates space for questions without judgment — a quality that has real impact on psychological safety, particularly for less experienced teammates.

Deniz also took on mentorship of two junior engineers this cycle, an investment that goes beyond role expectations at Senior level and signals emerging leadership potential.

One area to work on: receiving decisions that go against a stated technical position. Deniz has strong opinions — which is valuable — but a few design review moments this cycle became tense when the outcome didn't align with Deniz's recommendation. The goal isn't less conviction; it's separating advocacy from acceptance. Disagreeing and committing, and doing so visibly, builds the credibility that makes future technical influence more effective.

---

### Growth & Development — H2 Focus Areas

1. **Stakeholder-calibrated communication** — Practice the "decision first, detail second" writing pattern for documents that cross engineering boundaries.
2. **Early risk signaling** — Build the habit of flagging scope or timeline uncertainty at the moment it's identified, not after it has materialized.
3. **Graceful disagreement** — Develop a consistent practice of committing publicly and constructively when a decision goes another way, even when you'd have chosen differently.

---

### Summary

Deniz had an exceptional first half. The auth migration alone would have made this a strong cycle; the leadership coverage during parental leave elevated it further. The development areas are real — and worth taking seriously — but they're the growing edges of a Senior engineer on a clear path toward Staff-level contribution.

---

## How to Use This Skill in Claude

**Basic prompt:**
> Use the Performance Review Writer skill. Here is my input: [paste your `<review_input>` block]

**With additional instructions:**
> Use the Performance Review Writer skill. My company uses the format: [Summary / Strengths / Areas for Growth / Goals]. Adapt the output to that structure. Input: [paste block]

**For a promotion packet:**
> Use the Performance Review Writer skill. This review will accompany a promotion case to Staff Engineer. Emphasize scope, influence, and evidence of operating above level. Input: [paste block]

---

## Variations

### Variation 1 — Adapt to Your Company's Review Template
If your HR system requires a specific structure (e.g., "What Went Well / Even Better If / Goals"), tell Claude the required sections and it will reorganize the output accordingly.

### Variation 2 — Bias Check Only
If you've already drafted a review and want a second pass, ask:
> Review this draft for recency bias, halo effect, and gender-coded language. Flag any issues and suggest rewrites.

### Variation 3 — Low-Notes Mode
If your notes are sparse, Claude will ask clarifying questions before drafting. Prompt with:
> I have very limited notes. Ask me questions to gather enough information for a fair review before drafting.

### Variation 4 — Sensitive Situations
For underperformance, PIPs, or difficult feedback:
> This review involves an underperformance situation. Be direct and specific, avoid softening language that obscures the severity, and include clear expectations for the next cycle.

### Variation 5 — Promotion Calibration Language
> This engineer is being considered for promotion to [level]. Highlight evidence of scope expansion, influence beyond the team, and operating above current level expectations.

---

## Tips for Better Output

- **More notes = better reviews.** Even messy Slack messages or rough bullet points help Claude ground the review in specific evidence.
- **Include peer feedback verbatim** when you have it — Claude will paraphrase and synthesize it appropriately.
- **Name the level.** Knowing whether someone is L3 vs. Staff changes what "exceeds expectations" means and how Claude frames growth areas.
- **Don't pre-edit your notes.** The skill is designed for raw input. Cleaning up before pasting often removes the specific detail that makes reviews credible.
