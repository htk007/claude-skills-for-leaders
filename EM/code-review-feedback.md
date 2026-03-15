---
name: code-review-feedback-generator
description: "Use this skill when a Tech Lead or Engineering Manager needs to write code review comments. Triggers: any request involving reviewing a pull request, giving feedback on code quality, writing constructive criticism on code, generating code review summaries, or turning rough notes into structured review comments. Also use when the reviewer wants to make feedback more professional, less harsh, or more actionable. Do NOT use for debugging code or explaining how code works."
---

# Code Review Feedback Generator

## Overview

Writing good code review feedback is hard. It needs to be:
- **Clear** — the author understands what to change and why
- **Constructive** — it helps growth, not defensiveness
- **Consistent** — same standards applied across the team
- **Efficient** — you shouldn't spend 45 minutes writing comments

This skill turns your raw observations into structured, professional code review feedback.

---

## What This Skill Does

Given a code snippet and your rough notes, it generates:

1. A **summary comment** (overall PR assessment)
2. **Inline comments** per issue (with severity level)
3. A **closing note** (tone calibrated to situation)

---

## Severity Levels Used

| Level | Label | When to Use |
|-------|-------|-------------|
| 🔴 | `[BLOCKING]` | Must be fixed before merge |
| 🟡 | `[SUGGESTION]` | Should fix, but not blocking |
| 🔵 | `[NIT]` | Minor style or preference |
| 💡 | `[IDEA]` | Optional improvement worth considering |

---

## How to Use

Paste code + your rough observations in this format:

```
CODE:
[paste the code or diff here]

MY NOTES:
[paste your raw observations, even bullet points or messy notes]

CONTEXT:
- Author seniority: [junior / mid / senior]
- PR type: [feature / bug fix / refactor / hotfix]
- Tone preference: [direct / encouraging / neutral]
```

Claude will output structured, ready-to-post review comments.

---

## Example Input

```
CODE:
async function getUser(id) {
  const user = await db.query(`SELECT * FROM users WHERE id = ${id}`);
  return user;
}

MY NOTES:
- sql injection risk here
- should use parameterized query
- also no error handling at all
- variable name is fine

CONTEXT:
- Author seniority: junior
- PR type: feature
- Tone preference: encouraging
```

## Example Output

---

**📋 PR Summary**

Good progress on the user retrieval logic — the structure is clean and easy to follow. There are two important issues to address before merge, both very common when starting out with database queries.

---

**🔴 [BLOCKING] — SQL Injection Vulnerability**

```js
// ❌ Current
const user = await db.query(`SELECT * FROM users WHERE id = ${id}`);

// ✅ Fix
const user = await db.query('SELECT * FROM users WHERE id = $1', [id]);
```

String interpolation directly into SQL queries creates a SQL injection vulnerability — an attacker could pass a malicious `id` value and access or destroy data. Always use parameterized queries when user input touches a SQL statement. This is one of the most important security habits in backend development.

---

**🟡 [SUGGESTION] — No Error Handling**

If the database query fails (e.g., connection timeout, invalid ID format), the function will throw an unhandled exception. Consider wrapping in a try/catch:

```js
async function getUser(id) {
  try {
    const user = await db.query('SELECT * FROM users WHERE id = $1', [id]);
    return user;
  } catch (err) {
    logger.error(`Failed to fetch user ${id}:`, err);
    throw new Error('User fetch failed');
  }
}
```

---

**✅ Closing Note**

Nice work overall — the function signature and async/await usage are correct. Fix these two items and this is good to go. Feel free to ping me if you have questions on parameterized queries, happy to walk through it.

---

## Variations

**"Just give me bullet points, I'll write the comments myself"**
→ Ask: *"List the issues only, no full comments"*

**"I need a full PR summary comment only"**  
→ Ask: *"Write only the top-level PR summary, 3-5 sentences"*

**"The author is senior and I want to be direct"**  
→ Specify in CONTEXT: `Tone preference: direct`

---

## Tips for Best Results

- The more specific your notes, the better the output
- Always specify author seniority — it changes the tone significantly
- For hotfixes, mention it — the skill will deprioritize nits automatically
- You can paste a GitHub diff directly as the CODE section
