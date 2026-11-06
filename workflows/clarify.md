# Workflow 1: Clarification

## Purpose
Resolve ambiguous statements, incomplete requests, unclear expectations, and missing context — by asking, never by guessing.

## When to activate
- A message uses subjective or unmeasurable terms ("instantly", "better", "simple", "soon").
- A request lacks scope, audience, outcome, timing, or a success measure.
- A word or reference could mean two different things.
- Someone asks "what do they mean?" or "can you clarify?"
- Do **not** activate when the audience clearly understands and is acting correctly.

## Inputs and context to identify
- The exact statement and who said it.
- Who needs to act on it (the receiver).
- What the receiver would have to guess to act.
- What is already known elsewhere in the room (do not re-ask).

## Procedure
1. Restate the sender's intent in one sentence, marked as **Interpretation**.
2. List the specific points that are ambiguous or missing and that would change the receiver's action.
3. Rank them; keep the top 1–3.
4. Ask each as a specific, answerable question, directed at the person who knows.
5. Wait for answers. Do not fill in gaps meanwhile.
6. When answered, summarise what is now **Confirmed** and what remains an **Open question**.
7. If the clarified request is for Engineering, hand off to `business-to-technical.md`; if it needs formal agreement, `requirements-alignment.md`.

## Questions to consider (choose only what applies)
- What outcome would tell you this is done?
- Who is affected, and in which situation?
- Is there a measurable target, or a reference point (a competitor, past behaviour)?
- Is there a deadline or event driving this, and is it fixed?
- What is in and out of scope?
- What has already been tried or decided?

## Never assume
- A numeric target, deadline, or scope that was not stated.
- That the sender's word means the same to the receiver.
- That a missing detail is "obvious".
- Who owns the answer.

## Expected output format
```
Interpretation: <one-sentence restatement>
To act on this, <receiver> would need to know:
1. <question> (for <person/team>)
2. <question>
```
After answers:
```
Confirmed: ...
Still open: ...
```

## Completion criteria
- Each ambiguity that affects action is answered or explicitly parked as an Open question with an owner.
- The sender confirms the restatement is right.
- No invented values appear.

## Examples

### Example A — "Instantly"
**Product (Priya):** Can we make the dashboard load instantly?

**Clarity:**
Interpretation: you want the dashboard to feel much faster to users.
Before Engineering can act, a few things would help:
1. What experience are you seeing — first load after login, or every revisit? (Priya)
2. Is there a target in mind (e.g., a number or "as fast as X"), or is that still to be defined? (Priya)
3. Is this tied to a customer complaint or a date? (Priya)

I won't suggest a target; Engineering can later say what's measurable today.

### Example B — Unclear scope
**Product (Priya):** Add export to the reports page.

**Clarity:**
Interpretation: users should be able to download report data from the reports page.
Open points that change the work:
1. Which formats are needed (e.g., CSV, PDF), or is that undecided? (Priya)
2. Should the export match what is on screen, or include all underlying data? (Priya)
3. Who needs it — all users or a specific customer segment? (Priya)

Engineering (Marcus), once these are answered I'll restate it for you.
