# Design workflow

Use this workflow to turn requirements and evidence into a behavioral product specification.

## 1. Establish the evidence boundary

Inventory the supplied requirements, user research, analytics, screenshots, design files, data shapes, code, components, tokens, tests, and platform constraints. Separate facts, observations, assumptions, and preferences.

Resolve an unknown before proceeding when it changes the primary task, product objects, navigation, permissions, destructive consequences, or success criteria. Otherwise make the smallest reversible assumption and label it.

Do not manufacture specificity to make the specification look complete. Product objects, fields, status models, navigation, business rules, permissions, shortcuts, breakpoints, exact target sizes, named accessibility standards, and service contracts must come from supplied evidence or appear explicitly as proposals requiring confirmation. Use qualitative requirements when the correct numeric threshold depends on the product, platform, or existing system.

## 2. Frame the product outcome

Capture only information that changes the interface:

- User and product outcome
- Primary and secondary roles
- Recurring tasks ordered by frequency, importance, and risk
- Entities, relationships, statuses, lifecycle changes, and permissions
- Data volume, variability, freshness, latency, and missing-value semantics
- Desktop, mobile, native, embedded, or constrained operating context
- Existing product and design-system constraints

Do not start with a component inventory or visual style.

## 3. Model tasks and flows

Describe the primary path as decisions and system responses:

```text
entry -> orientation -> user action -> pending response -> result -> next useful action
```

Add the alternate paths that materially change layout, actions, copy, or recovery:

- First use and returning use
- Create, inspect, edit, duplicate, archive, restore, and delete
- Valid and invalid input
- Available, empty, stale, partial, unavailable, and failed data
- Authorized, restricted, and prerequisite-blocked access
- Single-item and bulk work
- Immediate and long-running operations
- Safe, reversible, and irreversible changes

Use [patterns-states-responsive.md](patterns-states-responsive.md) to build the state matrix.

## 4. Shape information from the task and data

For each important data group, state:

- The user question it answers
- Whether exact lookup, comparison, trend, sequence, distribution, composition, or status matters
- Necessary scope, labels, units, freshness, and baseline
- The appropriate representation and why
- The action or detail path it supports

Reject a chart, timeline, card, or story when a simpler representation serves the question better.

## 5. Define screen responsibilities and hierarchy

Organize regions by responsibility:

1. **Context** — location, object, account, workspace, or scope
2. **Orientation** — status, time range, filters, selection, or progress
3. **Primary work** — information and controls for the main task
4. **Actions** — the current mutation or navigation choices
5. **Support** — metadata, history, explanation, or help
6. **Feedback** — pending, saved, failed, restricted, or complete state

Write the reading order and action priority before styling. Remove equal-weight regions, redundant controls, and containers without a behavioral purpose.

## 6. Define disclosure and interaction surfaces

For every control or information group, classify it as frequent/required, secondary, advanced, conditional, or destructive. Keep frequent and required items explicit. Give every disclosed item a predictable trigger and preserve keyboard and touch access.

Choose inline interaction, popover, modal, drawer, page, or focused workspace from:

- Task duration and complexity
- Need to preserve surrounding context
- Interruption and blocking behavior
- Deep-link, collaboration, or history requirements
- Validation and destructive risk
- Available viewport and input method

Do not select a surface merely because a source or admired product demonstrated it.

## 7. Assign component contracts

For each component, define:

- Information displayed and action accepted
- State owned and state received
- Validation or business rule enforced
- Pending, success, and failure feedback
- Missing, long, delayed, and restricted content behavior
- Responsive transformation and input alternatives

Split components by coherent behavior and ownership. Scale shared components and tokens to actual repetition and team needs.

## 8. Define feedback, trust, and accessibility

Specify acknowledgement, pending behavior, success confirmation, failure recovery, focus movement, and preserved input for each mutation. Use optimistic feedback only under the conditions in [product-interface-principles.md](product-interface-principles.md).

Specify semantic controls, names, keyboard order, visible focus, announcements, non-color meaning, zoom and text expansion, reduced motion, and alternate input paths.

## 9. Transform across contexts

For wide, medium, and narrow contexts, state what remains simultaneous, what stacks, what becomes a focused mode, what moves behind disclosure, and how wide data is handled. Adapt to touch, keyboard, pointer, and platform conventions.

Do not write “make responsive” or proportionally scale a desktop composition.

## 10. Deliver the specification

Keep the result proportional to the request. Start with decisions that are supported or necessary; do not enumerate fictional fields, APIs, shortcuts, or edge cases. Use these labels consistently:

- **Fact** — stated in requirements or directly observed
- **Assumption** — reversible interpretation used to continue
- **Proposal** — recommended behavior that the product has not established
- **Open decision** — consequential choice that needs product input

```text
Screen or flow: [name]
Outcome: [user result]
Evidence: [supplied facts and observable artifacts]
Assumptions: [small reversible interpretations]
Proposals: [recommended but unestablished behavior]
Open decisions: [consequential choices requiring input]

Tasks and flow:
- [entry] -> [decision/action] -> [system response] -> [recovery/next action]

Data and representation:
- [user question] -> [representation and reason]

Structure and hierarchy:
1. [region] — [responsibility and priority]

Interactions:
- [trigger] -> [surface/transition] -> [feedback and recovery]

Components:
- [component] — owns [contract]; handles [states]

State matrix:
- [state] — [presentation, actions, accessibility, recovery]

Responsive transformations:
- Wide / medium / narrow / input-method differences

Acceptance criteria:
- Observable behavior, states, accessibility, risk, and edge cases
```

## Completion gate

Complete the Design workflow only when the specification covers the outcome, evidence and assumptions, primary and alternate flows, data representations, hierarchy, interaction surfaces, component contracts, applicable states, responsive transformations, accessibility, feedback, recovery, and observable acceptance criteria.
