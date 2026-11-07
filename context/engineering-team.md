# Engineering Team : General Reference Profile

> **This is a general reference profile, not an assumption about your organisation.** Companies differ in roles, stacks, processes, and vocabulary. Edit this file to reflect your own architecture, terminology, and practices (see the README section "Customising department context"). If the room contradicts this file, trust the room.

## Typical responsibilities
- **Architecture:** structuring systems and components so they can evolve safely.
- **Technical feasibility:** judging whether, how, and at what cost something can be built.
- **Implementation complexity:** understanding what is involved beyond the visible feature.
- **Dependencies:** other teams, services, libraries, data, infrastructure, or sequencing constraints.
- **APIs:** contracts between systems and clients.
- **Database considerations:** schema, queries, migrations, data volume, consistency.
- **Performance:** latency, throughput, resource use, scalability.
- **Reliability:** uptime, failure handling, monitoring, incident response.
- **Technical debt:** past shortcuts that increase the cost or risk of future change.
- **Security:** authentication, authorisation, data protection, compliance.
- **Testing:** unit, integration, end-to-end, regression, performance tests.
- **Deployment:** build, release, rollout, rollback, environments.
- **Engineering estimates:** forecasting effort and uncertainty.

## Common vocabulary (and what it often means)
| Term | Typical meaning | Watch out for |
|---|---|---|
| Latency | Time for a request to complete | Product may think "load time" means one number |
| Synchronous / asynchronous | Waiting vs. not waiting for a result | Business consequence often unstated |
| Lazy-loading | Loading parts of a page only when needed | May not speed up the *total* work |
| Refactor | Restructuring code without changing behaviour | Seen as "no user value" by Product |
| Technical debt | Cost of earlier shortcuts | Can sound like an excuse without a concrete impact |
| Dependency | Something this work needs before/while it proceeds | Often a blocker for a different team |
| Spike | Time-boxed investigation | Output is knowledge, not a feature |
| Estimate | Forecast with uncertainty | Often heard as a promise |
| Rollout / feature flag | Gradual or conditional release | Affects launch scope and risk |
| Scalability | Behaviour as load/data grows | Rarely tied to a concrete threshold |

## Typical priorities
Correctness, reliability, security, maintainability, predictable delivery, avoiding rework.

## Typical concerns
- Vague or shifting requirements.
- Estimates being treated as commitments.
- Pressure to cut testing, security, or foundational work.
- Hidden complexity and cross-system dependencies not visible to stakeholders.

## Communication patterns
- Frames answers in terms of components, constraints, risks, and trade-offs.
- Tends to be precise and caveated; may omit the customer-facing consequence.
- Needs requirements translated into **concrete behaviour, measurable targets, and scope boundaries**.
- Uses terms with exact meanings that can sound abstract or negative to non-engineers.

## What Xander should keep in mind
- Preserve technical caveats and uncertainty when translating; do not turn "likely" into "will".
- Ask Product for the user problem and measure rather than inventing a technical target.
- Do not estimate effort or assert feasibility; relay what Engineering said and ask when it is missing.
