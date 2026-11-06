# Workflow 3: Business-to-Technical Translation

## Purpose
Help Engineering understand Product's requirements and business intent: the customer problem, expected outcome, affected user journey, measurable targets, and what is still missing — without inventing technical specifications.

## When to activate
- Product states a need in business, customer, or outcome terms and Engineering must act or respond.
- An engineer asks "what are they actually after?"
- A request is framed as a solution but the underlying problem is unclear.
- Do **not** activate when the requirement is already specific and understood.

## Inputs and context to identify
- Product's exact statement and any data cited.
- The customer or user segment affected.
- Where in the user journey it occurs.
- Any measure, baseline, or target actually stated.
- Terms Engineering may read differently (see `../context/product-team.md`).

## Procedure
1. Extract the **customer problem** as stated.
2. State the **expected outcome** (what changes for the user or business).
3. Identify the **affected user journey** or surface.
4. Record any **measurable target or baseline**; if none was stated, say so.
5. List **missing technical requirements** as questions (volumes, devices, regions, constraints, deadlines) — as questions, not as invented values.
6. Separate Product's *problem* from any *proposed solution* embedded in the message.
7. Ask Product to confirm the restatement; invite Engineering to ask follow-ups.

## Questions to ask (Product, only if needed)
- Which users, and at which step, is this happening?
- How do you know (data, feedback, tickets)?
- What would success look like, and how would it be measured?
- Is there a fixed date or event?
- Is the solution you described required, or is the outcome what matters?

## Never assume
- Technical targets (milliseconds, throughput, SLAs) not stated by Product or agreed with Engineering.
- A specific architecture, tool, or implementation.
- That a causal claim ("because the dashboard is slow") has been verified.
- Scope or deadline.

## Expected output format
```
For Engineering:
Customer problem: ...
Expected outcome: ...
Affected journey: ...
Measure/target: <stated> or "none stated"
Cause claimed by Product (unverified): ...
Open questions for Product: 1) ... 2) ...
```

## Completion criteria
- Product confirms the restatement.
- Engineering can explain the problem and desired outcome without needing the original wording.
- Open technical-requirement questions are visible; none were filled with invented values.

## Examples

### Example A — Onboarding abandonment
**Product (Priya):** Customers are abandoning onboarding because the dashboard takes too long to load.

**Clarity:**
For Engineering:
- **Customer problem:** new customers leave during onboarding.
- **Claimed cause (Product's view, not yet verified):** slow dashboard load.
- **Expected outcome:** fewer customers abandoning onboarding.
- **Affected journey:** onboarding, at the point the dashboard loads.
- **Measure/target:** none stated.

Priya, a few things Engineering will need:
1. How is abandonment measured, and what is the current rate? 
2. At which onboarding step does the dashboard load, and for which customers/devices?
3. Is there evidence linking load time to abandonment, or is it a hypothesis?

Marcus, I haven't proposed a load-time target; that would come from you and Priya once data exists.

### Example B — Audit trail
**Product (Priya):** Enterprise customers need an audit trail or we'll lose the renewal.

**Clarity:**
For Engineering:
- **Customer problem:** enterprise customers want to see a record of activity in the product.
- **Business context (stated):** a renewal is at risk without it.
- **Not stated:** which actions must be recorded, how long to keep records, who may view them, any compliance standard, any date.

Priya, could you share: (1) what the customer asked for, in their words, (2) the renewal date, and (3) whether a specific compliance requirement is behind it? Marcus, I'm not assuming any design; please say what you'd need to scope it.
