# TC-06: Proactive Ambiguity Detection and Scope Preservation in Natural Conversation

| Field | Detail |
|---|---|
| Test ID | TC-06 |
| Agent under test | Xander, Product-Engineering Communication Generalist |
| Capability under test | Intervene in an unstructured conversation and preserve the resulting agreement |
| Test environment | Switch Console, private Direct Chat |
| Result | **Passed** |

## Objective

Verify that Xander can recognise ambiguity in an ordinary, unstructured Product-Engineering conversation without being explicitly instructed to perform an analysis (Stage A), and that it can preserve the scope decision once the teams clarify it (Stage B).

## Test input

**Stage A: natural conversation prompt**

```text
Product: We need the export feature to be faster. Customers are waiting too long.

Engineering: We can improve the processing pipeline, but we need to understand which export formats are most frequently used.

Product: Most customers use PDF, but we cannot ignore CSV exports either.
```

**Stage B: follow-up prompt**

```text
Product: Let's prioritise PDF exports for the first improvement. CSV must remain fully supported, but it doesn't need performance improvements in this first pass.

Engineering: Understood. We'll investigate PDF performance improvements while preserving existing CSV functionality. We'll share feasibility and baseline measurements before proposing an implementation.
```

## Expected behaviour

- Stage A: Recognise the confirmed information: export speed is a concern, PDF is most used, and CSV must not be ignored.
- Stage A: Avoid treating Engineering's pipeline comment as an approved implementation.
- Stage A: Identify the unresolved priority between PDF and CSV.
- Stage A: Avoid inventing a performance target or implying that CSV performance improvements are guaranteed.
- Stage A: Ask one useful question about the first improvement pass.
- Stage B: Record PDF performance investigation as the first-pass focus.
- Stage B: Preserve full CSV support while recognising that CSV performance work is outside this pass.
- Stage B: Record feasibility and baseline measurements as Engineering's next investigation output.
- Stage B: Recognise that no implementation has yet been proposed or approved.
- Stage B: Avoid asking for clarification when the scope and sequence are already clear.
- Stage B: Keep remaining questions, such as the definition of "good enough", separate from the agreed scope.

## Observed result

- Stage A: Xander intervened without an explicit instruction to find ambiguity. It identified the format-priority question and asked whether PDF should receive priority or both formats should receive equal priority.
- Stage B: Xander captured the PDF-first scope, retained CSV support, recognised the feasibility and baseline report as the next step, and did not manufacture a clarification question.

## Refinement identified

Stage A: preserve two wording details. (1) Engineering identified the processing pipeline as an area to investigate; it did not say investigation must wait until Product decides format priority. (2) "CSV must not be ignored" means CSV must remain in scope or supported; it does not automatically create a performance non-regression commitment.

Stage B: No material correction required. This follow-up demonstrates that Xander can preserve an agreement reached through a natural conversation.

---
Part of the [Xander Functional Validation Report](../Xander_Functional_Validation_Report.md).
