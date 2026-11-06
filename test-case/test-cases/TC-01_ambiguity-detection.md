# TC-01: Ambiguity Detection and Targeted Clarification

| Field | Detail |
|---|---|
| Test ID | TC-01 |
| Agent under test | Xander, Product-Engineering Communication Generalist |
| Capability under test | Identify missing information in an unclear Product request |
| Test environment | Switch Console, private Direct Chat |
| Result | **Passed** |

## Objective

Verify that Xander can identify ambiguity in a broad Product request, ask the single most important clarification question, and explain what Engineering needs before estimating or implementing.

## Test input

**Test prompt**

```text
Act as Xander, the Product and Engineering Communication Generalist.

A Product Manager sends this message:

"Can we make the dashboard load instantly? Customers are complaining."

Your task:
1. Identify what is ambiguous.
2. Ask only the most important clarification question.
3. Do not assume a performance target or implementation.
4. Explain what information Engineering needs before estimating or implementing this.
5. Keep the response concise.

Distinguish confirmed facts, assumptions and unresolved questions.
```

## Expected behaviour

- Identify that "instantly" is undefined and not a measurable target.
- Avoid assuming which dashboard interaction is slow.
- Separate confirmed facts from assumptions.
- Ask one high-value question that helps identify the affected customer experience.
- Explain the information Engineering needs before estimating or selecting an approach.
- Avoid inventing a latency target or implementation.

## Observed result

- Xander separated confirmed facts, assumptions and open questions.
- It identified the undefined meaning of "instantly" and asked which part of the dashboard experience customers were waiting for.
- It also outlined the information Engineering would need.

## Refinement identified

Resolve the affected user experience first (for example, first useful content, the full dashboard, or a specific widget) rather than bundling several questions about scope and performance targets into one.

---
Part of the [Xander Functional Validation Report](../Xander_Functional_Validation_Report.md).
