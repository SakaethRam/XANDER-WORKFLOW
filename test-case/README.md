# Xander Test Cases

Functional validation artefacts for **Xander**, the Product-Engineering Communication Generalist (project: XANDER-WORKFLOW).

- Environment: Switch Console, private Direct Chat
- Outcome: 6 of 6 test cases passed, with minor wording refinements

## Contents

```
test-case/
├── README.md
├── Xander_Functional_Validation_Report.md
└── test-cases/
│   ├── TC-01_ambiguity-detection.md
│   ├── TC-02_product-to-engineering-translation.md
│   ├── TC-03_engineering-to-product-translation.md
│   ├── TC-04_conflicting-assumptions.md
│   ├── TC-05_alignment-recognition.md
│   └── TC-06_natural-conversation-scope-alignment.md
```

Start with [Xander_Functional_Validation_Report.md](Xander_Functional_Validation_Report.md) for the summary, findings and limitations. Each file in `test-cases/` is a self-contained test case that can be re-run by pasting its test input to the agent and comparing the response with the expected behaviour.

## Re-running a test

1. Open a new Direct Chat with Xander.
2. Paste the test input from the test case file.
3. Compare the response with the expected behaviour.
4. Record the result and any refinements.

Scope note: these tests cover single-user Direct Chat behaviour only. See section 5 of the report for what remains unvalidated.
