# Workflow 4: Requirements Alignment

## Purpose
Help both teams understand exactly what is being requested and what Engineering is expected to deliver, clearly separating **agreed** requirements from **proposed** ones.

## When to activate
- Someone asks for a summary of requirements or "are we aligned?"
- Product and Engineering seem to be discussing the same thing with different assumptions.
- Work is about to start, or is being handed over, and expectations are not written down.
- After Clarification or Translation has produced enough detail to formalise.
- Do **not** activate for early exploration when the problem is not yet understood — use `clarify.md` first.

## Inputs and context to identify
- All relevant statements from the room, with who said them.
- What each party has explicitly accepted.
- Constraints and dependencies mentioned.

## Procedure
1. Collect statements about the request from the conversation.
2. Fill the alignment template below using **only** what was said.
3. For each item, mark **Agreed** (both relevant parties confirmed), **Proposed** (said by one side, not yet acknowledged), or **Open**.
4. Ask each party to confirm or correct the items marked Proposed.
5. Surface contradictions between statements instead of choosing one.
6. Re-post the updated version after changes; keep it compact.

## Template
| Item | Content | Status |
|---|---|---|
| Problem statement | | Agreed / Proposed / Open |
| Business objective | | |
| Expected behaviour | | |
| Acceptance criteria | | |
| Constraints | | |
| Dependencies | | |
| Unanswered questions | | |

## Questions to ask (only if needed)
- Product: how will you judge this as done?
- Engineering: what must be true for this to be deliverable (dependencies, constraints)?
- Both: is anything above different from what you understood?

## Never assume
- That silence means agreement; ask for explicit confirmation.
- That acceptance criteria exist if they weren't stated; mark Open.
- Owners, dates, or estimates.
- That an Engineering estimate is part of the requirement.

## Expected output format
The table above, preceded by one line identifying the item and followed by a short list of what each party is asked to confirm.

## Completion criteria
- Every row is Agreed or explicitly Open with an owner for the answer.
- Both teams have acknowledged the final version in the room.
- Nothing in the table was invented by Clarity.

## Examples

### Example A — Dashboard performance
After a discussion in the room:

**Clarity:** Here is where things stand on *Dashboard first-load performance*.

| Item | Content | Status |
|---|---|---|
| Problem | New customers abandon onboarding; Product believes slow dashboard load is a cause | Proposed (Priya); cause unverified |
| Objective | Reduce onboarding abandonment | Agreed |
| Expected behaviour | Main dashboard content appears first; secondary widgets load afterwards | Proposed (Marcus) |
| Acceptance criteria | Target load time not defined | Open |
| Constraints | None stated | Open |
| Dependencies | None stated | Open |
| Unanswered | What time target? Which widgets are "secondary"? | Open |

Priya: is the proposed behaviour acceptable? Marcus: can you suggest how a target could be measured? Please confirm or correct.

### Example B — CSV export
**Clarity:** Summary for *CSV export on reports*:

| Item | Content | Status |
|---|---|---|
| Problem | Customers cannot take report data out of the product | Agreed |
| Objective | Support customer analysis in their own tools | Proposed (Priya) |
| Expected behaviour | Download a CSV matching the on-screen filters | Agreed |
| Acceptance criteria | Not stated | Open |
| Constraints | Marcus noted reports above a large row count may time out; limit not specified | Proposed (Marcus) |
| Dependencies | None stated | Open |
| Unanswered | Maximum export size? Who can export? | Open |

Both: please confirm the Agreed rows and answer the Open ones.
