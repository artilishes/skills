---
name: apply-engineering-principles
description: Apply maintainability, architecture, security, data ownership, reliability, operability, and client-handover principles to consequential engineering work. Use for technical planning, architecture, platform or dependency decisions, sizeable implementations or refactors, code or architecture reviews, migrations, integrations, and foundational systems such as authentication, authorization, payments, multi-tenancy, and data modeling. Do not use for trivial edits, mechanical formatting, or narrowly prescribed changes that require no engineering judgment.
---

# Apply Engineering Principles

Ground engineering judgment in repository evidence, project constraints, risk, and long-term ownership. Prefer the smallest adequate and reversible solution over novelty, speculative scale, or local elegance.

Read [engineering-principles.md](references/engineering-principles.md) before making a recommendation or consequential change. Treat it as a shared taste file, not as a substitute for supplied requirements or repository-specific instructions.

## Establish the context

1. Read relevant project instructions, architecture notes, and decision records.
2. Inspect nearby code, tests, schemas, integrations, and established conventions before proposing or editing.
3. Identify the user or business outcome, current system behavior, explicit constraints, and actual source of truth.
4. Separate observed facts, supplied requirements, assumptions, and proposals. State consequential uncertainty instead of hiding it.

Do not invoke an abstract principle to override stronger local evidence. If an existing convention is weak, explain the cost of changing it and improve it deliberately rather than bypassing it incidentally.

## Calibrate the rigor

Assess:

- **Impact**: What users, data, money, permissions, clients, or systems can be affected?
- **Reversibility**: Can the decision be rolled back or migrated incrementally?
- **Uncertainty**: How much of the behavior, requirement, or operating environment is unknown?
- **Operational span**: Who must deploy, monitor, support, and eventually change it?

Increase design detail, review depth, documentation, and verification as impact, irreversibility, uncertainty, or operational span increase. For low-risk work, keep the process light and make the targeted change.

## Select the workflow

### Decide or plan

1. Define the problem without embedding a preferred solution.
2. List hard constraints and the decision criteria that matter in this context.
3. Compare the status quo and credible alternatives. Include maintenance, operational, migration, security, and total-cost consequences where relevant.
4. Recommend one option and explain why it fits this project, team, lifecycle, and handover model.
5. Record risks, open questions, rollback or migration boundaries, and the evidence that would change the decision.

Use a lightweight decision record only when future maintainers may reasonably question the choice. Do not manufacture alternatives or documentation ceremony for a straightforward decision.

### Implement or refactor

1. Preserve established ownership and data boundaries unless changing them is part of the task.
2. Make the smallest coherent change that fully solves the problem; do not leave partial or knowingly temporary structure behind.
3. Keep control flow, coupling, validation, authorization, and failure behavior explicit.
4. Avoid new libraries, services, abstractions, or infrastructure unless their benefit exceeds their maintenance and operational cost.
5. Update tests and documentation at the level where the behavior or decision is owned.
6. Verify with the narrowest meaningful checks, increasing coverage for high-risk boundaries and failure paths.

### Review

1. Review the system fit, not only local bugs or style.
2. Distinguish correctness, security, data-integrity, and operational risks from maintainability preferences.
3. Support each finding with observable evidence and describe its concrete impact.
4. Prioritize by severity, likelihood, blast radius, and cost of later correction.
5. Recommend the smallest coherent improvement and explain how to verify it.

Do not report personal taste as a defect. Omit speculative findings that cannot be tied to the supplied artifact or repository evidence.

## Complete the work

Before finishing, confirm the applicable items:

- Required behavior and important user outcomes remain correct.
- Security, privacy, authorization, and data integrity are enforced at trusted boundaries.
- Ownership, source-of-truth, synchronization, and failure behavior are explicit.
- High-consequence side effects account for retries, idempotency, partial failure, and recovery where relevant.
- The design creates no unjustified dependency, abstraction, infrastructure, or operational burden.
- Migration, rollout, rollback, observability, and after-launch ownership are addressed when the change requires them.
- Accessibility and admin or client workflows receive appropriate product-level care.
- Temporary duplication, confusing naming, or scaffolding introduced by the change has been cleaned up.
- Verification is proportional to risk, and unverified behavior is reported accurately.

Lead the final response with the outcome. Include only material tradeoffs, assumptions, validation results, and remaining risks; do not turn every implementation into an architecture essay.
