---
name: adr-writer
description: >
  Use this skill whenever a Tech Lead or team member needs to document an architectural decision.
  Triggers include: phrases like "write an ADR", "document this decision", "architecture decision record",
  "we decided to use X, let's write it up", "log our tech choice", "record why we chose", or any request
  to capture a significant technical or structural decision with context and rationale. Also trigger when
  the user describes a decision that was made (or is being made) and wants to preserve the reasoning for
  future team reference. If the user mentions trade-offs, rejected alternatives, or a decision that affects
  system structure, default to producing an ADR even if they don't use that exact term.
---

Produces a clear, structured Architecture Decision Record (ADR) that captures the full context of a technical
decision — including the problem, options considered, trade-offs, and final rationale — in a format the whole
team can read and reference months or years later.

The user provides **decision context**: the architectural or technical decision being made (e.g., "we chose
PostgreSQL over MongoDB for our user data store"), along with any relevant background, constraints, options
that were evaluated, and the reasons the chosen option was selected. The user may supply this as a rough
description, bullet points, a meeting summary, or a few sentences — the skill shapes it into a complete ADR.

## Thinking Process

Before writing the ADR, understand the decision and commit to a clear framing:

- **Purpose**: This ADR exists so that future team members (including the current team, six months from now)
  can understand *why* a decision was made — not just what was decided. It prevents relitigating settled
  decisions and provides context when revisiting or reversing them.
- **Tone/Approach**: Technical and precise. A Tech Lead writes for an audience of peers and future engineers — not management. The language should be direct and engineering-native: reference system properties (latency, consistency, coupling, blast radius) where relevant. Avoid advocacy; present the reasoning honestly, including the downsides of the chosen path.
- **Constraints**: Must follow a consistent, scannable structure (Status, Context, Decision, Consequences).
  Should be self-contained — a reader unfamiliar with the moment of decision should be able to understand
  the full picture from the document alone. Should be concise enough to actually be read.
- **Differentiation**: A great ADR is not a summary of what was decided — it is a window into *the moment*
  of decision: what pressures existed, what was unknown, what was sacrificed, and what was gained. It reads
  like a thoughtful memo, not a form filled out after the fact.

**CRITICAL**: The value of an ADR lives entirely in its honesty and completeness. A document that only
records the winning option without capturing the alternatives and trade-offs considered is nearly worthless
for future teams. Every ADR produced by this skill must make the *reasoning* legible — including the
constraints that ruled options out, the risks accepted, and the conditions under which the decision should
be revisited. Write it as if the author will not be available to explain it later, because they won't be.

Then produce a **Markdown ADR document** that is:
- Self-contained and understandable by a new team member with no prior context
- Honest about trade-offs, risks, and the limitations of the chosen approach
- Structured for scannability (headers, short paragraphs, clear sections)
- Durable — written to remain useful as the system evolves around it

---

## ADR Structure Guidelines

Every ADR must include the following sections, in order:

**Title & Metadata**:
Use a short, decision-focused title (e.g., "ADR-007: Use PostgreSQL for User Data Storage").
Include: ADR number (if known), date, status (`Proposed` / `Accepted` / `Deprecated` / `Superseded`),
and the author or decision owner. If the ADR supersedes or is related to another, note it here.

**Context**:
Describe the situation that required a decision. What problem were you solving? What forces or constraints
were in play (team size, timeline, existing stack, scalability needs, cost, compliance, etc.)? What would
have happened without making a decision? This section should give a reader who wasn't in the room enough
background to evaluate the decision themselves.

**Decision Drivers**:
List the criteria that mattered most when evaluating options — e.g., operational simplicity, team
familiarity, query flexibility, cost, licensing, community support, consistency with existing system
contracts, or long-term maintainability by the current team. If an RFC or design review shaped these
drivers, reference it. Be specific — this makes the logic of the final decision traceable and defensible.

**Options Considered**:
For each option evaluated, provide a brief description and its key pros and cons in the context of this
decision. Do not write this as a generic comparison — frame each option's strengths and weaknesses
relative to *this team's* specific constraints and drivers. Include at least two alternatives, even if
they were quickly dismissed.

**Decision**:
State the chosen option clearly and directly. Then explain *why* it was chosen over the alternatives,
referencing the decision drivers. If the decision was a close call, say so. If it was unanimous, say so.
Attribute the decision to a role or group (e.g., "decided by Tech Lead after RFC review on 2025-03-10" or "agreed by the engineering team in architecture review").

**Consequences**:
Describe what happens as a result of this decision — both positive and negative. What does the team gain?
What is now harder or more constrained? What technical debt is accepted? What must be monitored or
addressed later? Include any follow-up actions or open questions this decision creates.

**Revisit Conditions** *(optional but recommended)*:
State the conditions under which this decision should be reconsidered — e.g., "if user base exceeds 10M
records and query latency degrades", or "if the vendor discontinues support". This transforms the ADR from
a static record into a living signal.

---

NEVER produce an ADR that: omits the alternatives considered (this is the most common failure mode);
presents the chosen option as obviously correct without acknowledging its trade-offs; uses vague language
like "it scales better" or "it's more maintainable" without explaining *in this context* why that is true;
fills sections with boilerplate that adds no information; or reads like marketing copy for the winning
technology.

Every ADR is a snapshot of a moment of judgment under uncertainty. The goal is not to make the decision
look good — it is to make the reasoning transparent so future teams can build on it, challenge it, or
supersede it with confidence.

**IMPORTANT**: ADR length should match decision complexity. A simple library choice might need only two
paragraphs per section; a multi-system architecture shift might require detailed tables and diagrams
references. Both are valid. What matters is that every section contains real, specific information — not
placeholder prose. An ADR with five honest sentences per section is far more valuable than one with five
padded paragraphs.

A well-written ADR is one of the highest-leverage artifacts a Tech Lead can produce: it compresses
weeks of context into a single readable document that prevents repeated debates, onboards new engineers
faster, and gives future architects the intellectual foundation to make better decisions. Write each one
as if it will be read by your most skeptical senior engineer two years from now — because it will be.
