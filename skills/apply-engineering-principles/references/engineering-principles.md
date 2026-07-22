# Engineering Principles

Use these principles for large technical decisions, sizeable implementation tasks, architecture reviews, and code reviews. They are a shared taste file for maintainable client projects, internal tools, and long-lived product systems—not a rulebook for every line of code.

## Contents

- [Decision model](#decision-model)
- [Working defaults](#working-defaults)
- [Architecture](#architecture)
- [Code quality](#code-quality)
- [Data, security, and integrations](#data-security-and-integrations)
- [Reliability and verification](#reliability-and-verification)
- [Platforms and operations](#platforms-and-operations)
- [Product and client work](#product-and-client-work)
- [Scale and foundations](#scale-and-foundations)
- [Documentation and reviews](#documentation-and-reviews)

## Decision model

### Satisfy hard constraints

Treat these as constraints rather than tradeable preferences:

- Required behavior and important user outcomes.
- Security, authorization, privacy, compliance, and data integrity.
- Explicit contractual, regulatory, client, and repository requirements.

Passing tests does not prove that these constraints are satisfied. Check whether the tests and implementation represent the real requirement and trusted system boundaries.

### Weigh contextual criteria

After satisfying hard constraints, weigh the criteria that matter for the decision:

- Maintainability, clarity, and explicit ownership.
- Reliability and long-term operability after launch.
- Consistency with the existing project and team capability.
- User and product impact.
- Delivery time and total cost, including the risks and maintenance they create.

Do not force these criteria into a universal strict order. Explain which criteria dominate in the current context and why. Do not optimize only for novelty, short-term speed, passing tests, or local elegance.

### Match rigor to risk and reversibility

Increase design rigor, documentation, and verification as impact, irreversibility, uncertainty, or operational span increase. Move quickly on reversible presentation details. Move carefully on authentication, authorization, payments, identity, multi-tenancy, data models, migrations, and integration boundaries.

When several options satisfy the constraints, prefer the smallest adequate and reversible solution. Preserve migration and rollback options where practical.

## Working defaults

- Prefer boring, explicit, readable solutions over clever abstractions.
- Fit the architecture to the real project, team, client, lifecycle, and handover needs.
- Make tradeoffs visible. Avoid unsupported claims such as “best practice” or “the modern way.”
- Follow existing conventions unless there is a clear reason to improve them deliberately.
- Keep changes targeted and reversible where practical.
- Refactor temporary, duplicated, or confusing code introduced by the current change before calling the work finished.
- Document decisions that future maintainers may reasonably question.

## Architecture

### Fit the project

Use architecture strong enough to support plausible future change without adding unnecessary operational burden. Before adding infrastructure, services, abstractions, or patterns, answer:

- What problem does this solve now?
- What plausible future change does this make easier?
- What burden does it introduce?
- Who will maintain it after launch?

If the answer is unclear, prefer the simpler design.

### Keep structure visible

Make the system understandable at three levels:

- **Product**: What the system does for users and clients.
- **Architecture**: Main components, responsibilities, data ownership, and data flows.
- **Code**: Where a feature lives and how data moves through it.

Use diagrams, decision records, repository documentation, folder conventions, and naming when they clarify these levels. Use diagrams to explain boundaries or flows, not to decorate documentation.

### Prefer feature ownership when it fits

For larger applications, prefer feature-oriented organization when it makes ownership and change boundaries clearer. Let a feature own its local components, hooks, utilities, schemas, queries, mutations, and domain logic where practical.

Reserve global folders for truly shared building blocks: design-system components, generic utilities, shared configuration, app-level providers, and cross-cutting infrastructure. Avoid overloaded `components`, `utils`, or `hooks` folders. Do not reorganize a small or established project merely to conform to this preference.

### Use the right abstraction level

Create abstractions to reduce repeated complexity, not to hide important behavior. Wait until a stable pattern is visible. A good abstraction has a clear name, responsibility, and scope. A bad abstraction makes simple changes harder because maintainers must understand both the abstraction and the behavior it conceals.

## Code quality

### Optimize maintainability

Write code that is easy to understand, change, and delete. Make important assumptions visible through naming, structure, types, runtime validation, tests, or documentation. Good code does not only work; it communicates intent.

### Prefer readable control flow

Use control flow that is easy to scan. Avoid deeply nested ternaries, self-invoking functions in JSX, dense inline logic, and conditionals that depend on hidden context. Accept a few more lines when they reduce cognitive load.

### Keep shared UI generic

Name shared components and icons by what they are, not where they happen to be used. Prefer `ChevronRightIcon` over `HomeMenuIcon` when the icon is a chevron. Use `UserCard` only when it is a generic user card, not a one-page section.

Do not promote code to shared or global status too early. Duplication can be better than premature abstraction. Extract a shared pattern after repeated usage reveals stable behavior and ownership.

### Prefer deliberate consistency

A slightly imperfect pattern used consistently is often better than a perfect pattern used once. Check whether the project already has an established approach before introducing another one. If the existing pattern is weak, improve it deliberately instead of bypassing it randomly.

### Avoid hidden coupling

Do not rely on implicit relationships that are easy to break. Make coupling visible through types, schemas, interfaces, naming, documentation, tests, and module boundaries. Be especially careful with CMS schemas, payment states, identity IDs, tenant IDs, permissions, and cross-system synchronization.

### Add dependencies deliberately

Evaluate a new dependency by capability, maturity, maintenance activity, security posture, bundle or runtime cost, upgrade path, ecosystem fit, and ease of removal. Prefer an established dependency when it removes substantial commodity complexity. Prefer local code when the requirement is small and stable. Do not add a library merely to avoid writing a few clear lines.

### Measure before optimizing

Do not introduce caching, concurrency, denormalization, or architectural complexity for speculative performance. Establish the relevant workload and bottleneck first. Preserve clean boundaries that allow optimization when evidence appears.

## Data, security, and integrations

### Validate boundaries

Validate untrusted input at system boundaries: forms, API routes, server actions, webhooks, CMS data, third-party integrations, imports, and database writes. Static types help inside the system but do not replace runtime validation.

### Treat security and privacy as design work

Consider security early for authentication, authorization, file uploads, forms, payment flows, admin tools, and integrations. Do not trust client-side checks. Enforce important authorization rules on the server or another trusted boundary. Prefer established authentication and authorization systems over custom implementations unless there is a strong reason.

Collect, expose, and retain only the personal or sensitive data the product needs. Consider data classification, access, deletion, auditability, and retention alongside storage location and consent.

### Separate identity from product authorization when needed

When multiple products need shared accounts, prefer a central identity provider using standards such as OpenID Connect unless product, regulatory, or operational constraints justify separate identity systems. Let the identity system answer “who is this user?” and each product answer “what can this user do here?”

Do not introduce centralized identity for a small standalone product without a concrete ecosystem need.

### Define data ownership

For payment providers, CMSs, identity providers, CRMs, ATSs, external backends, and other integrations, define which system owns each kind of data. If multiple systems store similar data, define the source of truth, synchronization direction, conflict behavior, and recovery process.

### Design side effects for failure

Assume networks, providers, workers, and clients can retry, time out, duplicate requests, or fail partway through. Use idempotency, durable state transitions, reconciliation, and explicit retry policies where consequences justify them. Do not report success before the system has reached the state the product promises.

## Reliability and verification

### Verify behavior in proportion to risk

Use the narrowest checks that provide meaningful confidence, then increase coverage for high-impact or difficult-to-reverse work. A low-risk local refactor may need targeted tests and type checking. A payment, permission, migration, or synchronization change may require boundary tests, failure-path tests, staged rollout, observability, and rollback rehearsal.

### Test contracts and outcomes

Prefer tests that protect externally meaningful behavior, domain rules, interfaces, and regressions over tests coupled to incidental implementation details. Cover invalid input, authorization, empty and error states, partial failure, retries, and recovery when they are material to the workflow.

### Make failures understandable

Handle errors at the level that can add useful context or recovery. Preserve actionable diagnostic information without leaking secrets or sensitive data. Avoid silent failure, broad exception swallowing, and fallback behavior that hides data corruption or security problems.

### Treat migrations as product and operational work

Plan schema changes, data backfills, API transitions, and system replacements around compatibility, rollout order, data validation, monitoring, rollback, and ownership. Prefer expand-and-contract or other incremental approaches over synchronized rewrites when practical.

## Platforms and operations

### Use managed platforms when they remove irrelevant complexity

Managed hosting, databases, CMSs, and specialized SaaS tools are often appropriate when they remove undifferentiated infrastructure work. Evaluate vendor reliability, data access, portability, cost growth, support, security, compliance, and exit options. Do not build commodity systems unless custom ownership creates real value.

### Self-host only with strategic justification

Self-hosting can serve compliance, control, cost, resilience, or client requirements. This can matter especially for German and European clients with data-residency, GDPR, vendor, or supportability constraints. Self-hosting also creates operational responsibility. Do not choose a tool only because it is open source or appears cheaper on its pricing page.

### Design ownership after launch

Before launch, clarify:

- Who owns the system and can deploy it?
- Where are logs, metrics, and errors visible?
- Where is operational and architectural documentation?
- How are secrets managed and rotated?
- How are dependencies and platforms updated?
- How are incidents, backups, restores, and provider outages handled?

A technically good system that nobody can operate is not a good system.

### Treat observability as delivery work

Provide enough production visibility to understand failures, state transitions, and meaningful usage. Consider structured logging, error reporting, metrics, tracing, analytics, monitoring, audit history, and admin visibility according to risk. Keep telemetry proportionate and respect privacy, compliance, retention, and client expectations.

## Product and client work

### Keep client systems boring

Build client systems to be resilient, understandable, and supportable by small teams. Avoid choices that depend on niche expertise, fragile workflows, or individual developer memory. Work with client constraints instead of designing a perfect greenfield system that will not survive handover.

### Build admin experiences with care

Treat internal users, editors, admins, and client teams as product users. Prefer guided flows, sensible defaults, validation, previews, clear labels, recoverable actions, and useful documentation over exposing raw technical structure.

### Treat accessibility as product correctness

Use semantic controls, accessible names, logical focus, keyboard access, sufficient contrast, non-color status cues, and reduced-motion support where applicable. Include accessibility in requirements, implementation, and verification rather than postponing it as visual polish.

### Keep project boundaries clear

In agency work, make project and client ownership obvious. Avoid mixing unrelated concerns in one backlog, repository area, data store, or architecture unless it is a deliberate shared-platform decision. For shared services, define what is global, client-specific, and project-specific.

### Evaluate cost in context

Consider cost together with reliability, delivery speed, maintainability, portability, and operational effort. A cheaper system can become expensive through custom work or maintenance risk. An expensive tool can be justified when it removes significant complexity or risk.

## Scale and foundations

### Do not over-engineer hypothetical scale

Design for plausible growth, not fantasy growth. Prefer clean boundaries, clear data models, and operational visibility that allow the system to evolve. Avoid distributed systems, queues, caches, generalized platforms, and complex abstractions without evidence of need.

### Do not under-engineer foundations

Some decisions are expensive to fix later. Give authentication, authorization, payments, data modeling, multi-tenancy, content architecture, and integration boundaries appropriate design attention upfront. Move fast on reversible UI details and carefully on foundations.

### Prefer small migrations

Prefer incremental migrations over large rewrites. Identify boundaries such as authentication, checkout, billing, CMS, frontend, synchronization, and deployment. Move one boundary at a time, maintain compatibility during transition, verify migrated data, and preserve rollback options where practical.

## Documentation and reviews

### Make consequential decisions traceable

Use lightweight decision records for choices involving architecture, authentication, hosting, payments, CMS selection, data ownership, security, major dependencies, and other decisions future maintainers may reasonably question.

A useful decision record includes:

- Context and constraints.
- Options considered, including the status quo.
- Decision and rationale.
- Tradeoffs, risks, and consequences.
- Migration or rollback considerations.
- Open questions and evidence that could change the decision.

Do not document every small implementation choice.

### Keep documentation close

Use repository-level documentation for setup, architecture, conventions, and common workflows. Keep feature-level documentation near complex features. Documentation does not need to be long; it needs to answer questions future maintainers will actually have.

### Review the system, not just bugs

Review for correctness, user outcomes, readability, naming, structure, security, privacy, accessibility, data integrity, operability, consistency, and unnecessary complexity. Ask whether the code fits the surrounding system. Look for partial solutions that work locally but leave unclear ownership, failure behavior, or temporary complexity behind.

Protect maintainability and shared understanding without enforcing personal style preferences.

### Prefer practical standards

Use standards that the team can understand and apply consistently. Keep folder structures, naming rules, branching conventions, pull-request expectations, and review checklists simple. When a rule is repeatedly misunderstood, improve the rule, examples, tooling, or onboarding material.
