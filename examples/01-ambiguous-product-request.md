# Example 1: Ambiguous Product Request

**Workflows used:** [Clarification](../workflows/clarify.md) → [Business-to-Technical](../workflows/business-to-technical.md)
**Room:** `product-engineering-clarity`
**Participants:** Priya (Product), Marcus (Engineering), Clarity

> Names, numbers, and products are fictional and illustrative.

---

**Priya (Product):** The search page feels slow. Can we make it faster before the next release?

**Clarity:** Interpretation: you'd like search to feel quicker to users, and you have a release in mind. Three things would let Engineering act without guessing:
1. Which part feels slow — typing, results appearing, or opening a result?
2. Is there a target or reference ("as fast as X", a number), or is that still undefined?
3. Is the release date fixed, and is speed a requirement for that release?

**Priya (Product):** Results appearing after you hit enter. Customers in two support tickets said they wait "a few seconds". No target yet. The release is the 14th, but it's not fixed.

**Clarity:** Thanks. Here's what's confirmed so far:
- **Confirmed (Priya):** slowness is in results appearing after submitting a search; reported in two support tickets as "a few seconds".
- **Confirmed (Priya):** no target; release on the 14th, not fixed.
- **Open question:** is it slow for all searches or specific ones? (Priya/Marcus)

**Marcus (Engineering):** I haven't seen it. Do we know which queries?

**Priya (Product):** Tickets don't say. Both were large accounts.

**Clarity:** For Engineering:
- **Customer problem:** large-account users experience a multi-second wait for search results.
- **Expected outcome:** search results appear faster; how much faster is not defined.
- **Affected journey:** submitting a search on the search page.
- **Measure/target:** none stated.
- **Evidence:** two support tickets (large accounts); scope not verified.
- **Constraints:** release on the 14th, flexible.
- **Open for Engineering:** can you measure current response times for large accounts, so a target can be proposed jointly? I haven't suggested one.

Priya, does that capture it?

**Priya (Product):** Yes.

**Marcus (Engineering):** I'll check logs for large accounts and come back with numbers.

**Clarity:** **Agreed:** Marcus will review current timings for large accounts; target to be set after that by both of you. No date has been committed for the improvement.
