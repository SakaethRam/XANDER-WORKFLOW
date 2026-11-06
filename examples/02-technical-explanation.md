# Example 2: Technical Explanation

**Workflow used:** [Technical-to-Business Translation](../workflows/technical-to-business.md)
**Room:** `product-engineering-clarity`
**Participants:** Priya (Product), Marcus (Engineering), Clarity

> Names, numbers, and products are fictional and illustrative.

---

**Marcus (Engineering):** We can't do real-time notifications on the current setup. The notification service polls the database every 30 seconds and the table isn't indexed for that query. Moving to event-driven would fix it, but it touches the message queue and I'd want to load test first.

**Priya (Product):** Ok… so is that a no?

**Clarity:** For Product:
- **What Engineering means:** today the system *checks* for new notifications every 30 seconds ("polling"), so users can see them up to about 30 seconds late. The database lookup is also not set up to be fast for this ("not indexed"). 
- **What the proposal does:** "event-driven" means notifications are sent the moment something happens rather than found on a timer. It would involve changing how messages pass between services (the "message queue").
- **Why it matters:** users could receive notifications much closer to instantly. *(Interpretation — Marcus, please confirm.)*
- **Still uncertain:** Marcus wants to load test first (check it holds up under heavy use), so it isn't yet confirmed it works at scale. No estimate or date was given.
- **On "is that a no?":** Marcus said it can't be done on the *current setup*; he also described a way to do it. It sounds like "not as-is, possible with changes" rather than "no". Marcus, is that right?

**Marcus (Engineering):** Yes. Not as-is, possible with changes. And the polling interval could be shortened as a stopgap, but that increases database load.

**Clarity:** **Confirmed (Marcus):** a stopgap exists, shortening the polling interval, with a cost: more database load.
**Open questions:**
- Priya: how "real-time" do users need it to be (seconds? instant)?
- Marcus: can you give an estimate for the event-driven change and the load test?

**Priya (Product):** Within a few seconds is fine, honestly.

**Marcus (Engineering):** Then shortening to 5 seconds might be enough. I'll test the load impact.

**Clarity:** **Agreed:** try a shorter polling interval first (Marcus's example: 5 seconds), pending Marcus's load check. The event-driven approach is not ruled out, but not scheduled.
