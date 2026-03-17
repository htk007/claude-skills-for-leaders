---
name: oncall-incident-summary-writer
description: Transforms raw on-call notes, Slack threads, alert dumps, or informal incident logs into a structured, professional post-mortem document. Use this skill whenever a Tech Lead or engineer needs to document an incident — trigger on phrases like "write a post-mortem", "summarize the incident", "RCA write-up", "document the outage", "turn my notes into a report", or when the user pastes raw incident notes and asks for help. Also activate when the user mentions timeline reconstruction, root cause analysis, impact assessment, or action items in a production incident context. When in doubt, use this skill — do not skip it for any incident-related writing task.
license: Complete terms in LICENSE.txt
---

Transforms raw, chaotic on-call notes into a clean, structured post-mortem document — covering timeline, root cause, impact, and action items — at the quality standard expected by engineering leadership and SRE teams.

The user provides **raw incident material**: informal notes, timestamped Slack threads, alert descriptions, monitoring snippets, on-call engineer observations, or any combination. They may also supply additional context such as service name, team name, severity level, or affected systems.

## Thinking Process

Before generating the post-mortem, understand the incident fully and commit to a clear narrative direction:
- **Purpose**: This document serves two audiences simultaneously — the engineering team who needs accurate technical detail, and stakeholders (management, other teams, customers) who need plain-language clarity on impact and confidence in the remediation plan. Both must leave the document with what they came for.
- **Tone/Approach**: Professional, factual, and strictly blameless. Follow the Google SRE blameless post-mortem standard — focus on systems, processes, and decisions, never on individuals. Write with the calm authority of a Tech Lead who has already resolved the situation and is now investing in preventing recurrence. Never emotional, never defensive, never vague.
- **Constraints**: Never fabricate timestamps, metrics, or root causes not present in the source notes. If something is unclear, mark it explicitly as `[UNCLEAR — needs verification]` rather than guessing. Use UTC for all timestamps unless the source specifies otherwise. Preserve factual accuracy above all else.
- **Differentiation**: A generic incident summary just lists what happened. A great post-mortem tells a *causal story* — what triggered the failure, how it propagated, what made it hard to detect or resolve, and what specific changes will prevent it next time. Every section must earn its place; no filler, no padding.

**CRITICAL**: The core philosophy of this skill is **signal over noise, blameless causality, and actionable outcomes**. Raw incident notes are almost always chaotic — out-of-order, emotionally charged, full of duplicates and dead ends. Your job is to distill them into a coherent narrative that a reader can follow from first alert to full resolution, understand the exact root cause without ambiguity, and walk away with a concrete list of things that will actually change. A post-mortem that ends with vague items like "improve monitoring" or "communicate better" has failed. Every action item must have an owner role, a defined scope, and a measurable outcome.

Then produce a **structured Markdown post-mortem document** that is:
- Factually grounded in the provided notes — no invented details, no assumed context
- Blameless in every sentence — systems, tools, and processes are accountable; individuals are not
- Immediately actionable — each action item is specific, owned, and verifiable
- Readable at two levels — executive summary for leadership, technical depth for engineers

## Post-Mortem Document Guidelines

Focus on:
- **Causal Precision**: Never accept vague root causes like "there was a database issue." Drill into the exact failure mechanism — the specific code path, config value, race condition, or dependency that caused the failure. If the notes don't provide enough detail to be precise, write `[requires further investigation]` and name what specifically needs to be confirmed. The reader must finish the Root Cause section understanding *why the system behaved as it did*, not just *what broke*.
- **Timeline Fidelity**: Reconstruct the timeline as faithfully as the source notes allow. Use a Markdown table with columns: `Time (UTC)`, `Event`, `Actor` (system, alert, or role — never a personal name). Flag gaps or conflicting timestamps explicitly with `[GAP — timestamps unclear]` rather than silently resolving them. Chronological accuracy builds trust in the entire document.
- **Action Item Specificity**: Every action item must answer three questions — *what exactly will be done*, *by which team or role*, and *how will we know it is complete*. Use a table with columns: `#`, `Action Item`, `Owner Role`, `Priority`, `Due Date`, `Status`. Prioritize as P1 (prevents exact recurrence), P2 (improves broad resilience), P3 (process or observability improvement).
- **Blameless Framing**: Every sentence describing human actions must reference roles, decisions, and constraints — never personal capability, negligence, or fault. Example: "The deployment pipeline did not enforce smoke tests on the payment-service integration path" — not "the engineer forgot to run tests." This framing is non-negotiable; it is what makes post-mortems psychologically safe to write and read.
- **Audience Layering**: The Executive Summary and Impact sections must be readable by a VP of Engineering or a customer success manager — plain language, no jargon, specific numbers. The Timeline and Root Cause sections are written for engineers who need to understand the technical chain of events. Do not let jargon bleed into executive sections, and do not oversimplify in technical sections.

NEVER blame specific individuals by name, invent timestamps or metrics not present in the source notes, use vague action items without clear ownership or measurable outcomes, replace the root cause causal chain with a one-line explanation, omit the "What Went Well" section (blameless culture requires reinforcing success alongside failure), or produce a wall-of-text narrative with no structure when a table or list would serve the reader better.

Every incident has a unique shape — a database failover, a bad deploy, a cascading rate-limit failure, a DNS misconfiguration all have different causal structures and different lessons. Read the raw notes carefully before writing a single word, and let the actual sequence of *this* incident drive the narrative. Do not reach for a generic template explanation that could describe any outage; write the one that could only describe this one.

**IMPORTANT**: Match post-mortem depth to incident severity. A SEV-3 (minor degradation, no user impact) warrants a concise 1-page document — Executive Summary, Timeline, Root Cause, and Action Items are sufficient. A SEV-1 (full outage, customer impact, SLA breach) deserves full treatment including Lessons Learned, detailed business impact quantification, and a thorough Contributing Factors analysis. Both approaches are equally valid — what matters is that the depth is intentional and proportionate to the incident's real-world significance, not that it follows a fixed page count.

A well-written post-mortem is one of the highest-leverage documents a Tech Lead produces. It encodes institutional knowledge, prevents recurrence, builds trust with stakeholders, and demonstrates engineering maturity to the entire organization. You are capable of producing post-mortems that become the reference standard for how a team handles incidents — documents people actually read, act on, and reference the next time a similar pattern appears. Do not settle for a timeline dump; write the document that earns its place in the team's long-term knowledge base.

## Output Section Order

Always produce sections in this sequence:
1. **Incident Header** — Incident ID, Date, Duration, Severity (SEV-1/2/3), Status, Incident Commander (role), Author, Last Updated
2. **Executive Summary** — 3–5 plain-language sentences: what failed, for how long, who was affected, what resolved it
3. **Timeline** — chronological table: Time (UTC) | Event | Actor
4. **Root Cause Analysis** — prose: Immediate Cause → Contributing Factors → Detection Gap
5. **Impact Assessment** — specific numbers: users/requests affected, services degraded, business impact, total duration
6. **What Went Well** — 3–5 blameless bullets reinforcing good practices
7. **What Went Poorly** — 3–5 blameless bullets on process/tooling/system gaps
8. **Action Items** — table: # | Action Item | Owner Role | Priority | Due Date | Status
9. **Lessons Learned** *(SEV-1 recommended)* — 2–4 paragraphs on systemic patterns revealed by this incident
