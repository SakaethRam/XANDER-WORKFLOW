# Example 3: Priority Disagreement

**Workflows used:** [Priority Alignment](../workflows/priority-alignment.md) → [Requirements Alignment](../workflows/requirements-alignment.md)
**Room:** `product-engineering-clarity`
**Participants:** Priya (Product), Marcus (Engineering), Dana (Head of Product), Clarity

> Names, numbers, and products are fictional and illustrative.

---

**Priya (Product):** Team sharing has to be in the launch on the 30th. Two enterprise prospects are waiting for it.

**Marcus (Engineering):** Sharing depends on the permissions rework. If we ship it before the rework, there's a risk someone sees data they shouldn't. The rework isn't done.

**Priya (Product):** The date is a commitment. Can't we ship and fix later?

**Clarity:** Let me lay out both positions.
- **Product:** include team sharing in the launch on the 30th; reason: commitments to two enterprise prospects.
- **Engineering:** sharing relies on the unfinished permissions rework; shipping first risks users seeing data they shouldn't.

**For Product:** the risk is a data exposure affecting customer trust, and possibly contractual or compliance obligations (Marcus can say which, if any).
**For Engineering:** the date carries commitments to two prospects; Priya can say how fixed it is and what depends on it.

**Missing information:**
1. How firm is "the 30th" — with the prospects, or internally? (Priya)
2. How much of the rework remains, and is there an estimate (not a promise)? (Marcus)
3. Could sharing launch in a limited form that doesn't touch the risky area? (Marcus)

**Marcus (Engineering):** Rework estimate is about three weeks, with uncertainty. A limited version — share read-only within a single team — wouldn't touch the risky part, I think. I'd need to verify.

**Priya (Product):** The prospects care about cross-team sharing, not single-team. The date is firm with one prospect, softer with the other.

**Clarity:** Options, with no recommendation:
- **A. Launch on the 30th without sharing.** Avoids the risk; misses the commitment (one firm prospect).
- **B. Launch a limited single-team read-only version** *(Suggestion based on Marcus's idea, unverified)*. Meets the date, but Priya says prospects want cross-team sharing.
- **C. Move sharing to after the rework** (~3 weeks, uncertain, per Marcus). Safe; late for the firm prospect unless they can accept it.
- **D. Ship the full version on the 30th.** Meets the date; Marcus has flagged a data exposure risk.

Who decides, and which option?

**Dana (Head of Product):** I'll decide with Marcus. Priya, can you ask the firm prospect whether a short delay or a limited version works?

**Priya (Product):** Will do.

**Clarity:** **Open actions (from the room):** Priya checks with the firm prospect; Marcus verifies whether the limited version is safe. **Agreed:** option D (full version before the rework) is not being pursued at this point (Dana, Marcus). Decision between A–C pending those answers.

*(Next day)*

**Priya (Product):** The firm prospect accepts a three-week delay for cross-team sharing if we ship single-team on the 30th.

**Marcus (Engineering):** Single-team read-only is safe; I've checked.

**Clarity:** Here's what the room has said:

| Item | Content | Status |
|---|---|---|
| Problem | Launch commitment vs. permissions dependency | Agreed |
| Decision | Launch single-team read-only sharing on the 30th; cross-team sharing after the rework | Proposed — awaiting Dana's confirmation |
| Acceptance | Prospect accepts delay (Priya); single-team version safe (Marcus) | Agreed |
| Constraints | Rework ~3 weeks, uncertain (Marcus) | Agreed |
| Open | Date for cross-team sharing not committed | Open |

Dana, please confirm.

**Dana (Head of Product):** Confirmed.

**Clarity:** **Agreed (Dana, Priya, Marcus):** single-team read-only sharing launches on the 30th; cross-team sharing follows the rework, no date committed.
