# Implementation workflow

This workflow is an independent repository and verification guardrail. Do not attribute it to the video corpus.

## 1. Inspect before proposing

Locate the repository's actual:

- Application structure, routes, layouts, and entry points
- Similar product screens and interaction patterns
- Tokens, themes, type roles, spacing, elevation, and motion primitives
- Forms, validation, tables, charts, overlays, notifications, and navigation components
- Data contracts, permissions, loading, errors, mutations, and caching behavior
- Accessibility utilities and keyboard conventions
- Responsive conventions and supported contexts
- Tests, stories, fixtures, preview tools, and validation commands

Read implementations when behavior is unclear. Do not infer capability from a component name. Preserve unrelated user changes and distinguish an intentional pattern from legacy inconsistency.

## 2. Reconstruct the current product model

Trace the route context, data lifecycle, user role, permitted actions, main task, completion signal, state ownership, alternate states, and dependencies shared with other screens.

For a refactor, separate behavioral changes from structural and visual cleanup. Preserve working behavior unless the requested outcome changes it.

## 3. Map decisions to local contracts

Create a small mapping before coding:

| Need | Existing contract | Decision |
| --- | --- | --- |
| Page context | Shell, route, breadcrumb, or scope control | Reuse or extend |
| Primary task | Existing action and form conventions | Match or justify change |
| Data question | Table, list, summary, timeline, or chart | Select from task and data |
| Edit flow | Inline, overlay, page, or workspace | Select from scope and risk |
| Feedback | Local status, notification, or activity pattern | Cover pending, result, and failure |
| Responsive behavior | Existing breakpoints and transformations | Extend without one-off assumptions |
| Accessibility | Local primitives and utilities | Preserve semantics and focus |

Prefer composition over duplicating a near-identical component. Extend a shared component only when the new contract belongs to its other consumers.

## 4. Plan the smallest coherent change

Define files, data and state changes, reused and new primitives, interaction behavior, edge states, permissions, accessibility, responsive transformations, verification, and explicit non-goals.

Do not rewrite a design system to solve one screen. Introduce the smallest reusable addition only when an established contract cannot support required behavior.

## 5. Implement in behavioral order

When practical, build in this order:

1. Semantic structure and accessible names
2. Data flow, permissions, and state ownership
3. Primary task and action behavior
4. Validation, pending, success, failure, and recovery
5. Responsive and input-method transformations
6. Hierarchy and system-aligned styling
7. Purposeful motion and secondary polish

Use realistic long labels, large and missing values, empty collections, restricted roles, errors, and slow operations while implementing.

## 6. Preserve system integrity

- Reuse semantic tokens instead of isolated values.
- Keep action, status, and navigation language consistent.
- Keep business rules out of visual-only components.
- Preserve focus through overlays, validation, navigation, and asynchronous changes.
- Keep status understandable without color and actions reachable without hover or gesture.
- Explain unavailable actions when the reason helps users proceed.
- Do not import source-specific ratios, chart forms, layouts, or motion recipes unless the established system or explicit requirement calls for them.

## 7. Verify proportionally

Run the repository's relevant checks once per coherent change batch. Verify:

- Primary and alternate flows
- Loading, refreshing, empty, partial, error, disabled, restricted, pending, success, and destructive states
- Validation, permissions, duplicate submission, rollback, and recovery
- Narrow, intermediate, and wide layouts
- Long text, large data, missing values, and overflow
- Keyboard order, visible focus, names, announcements, and reduced motion
- Existing consumers of changed shared components
- Relevant automated checks and visual inspection

Compare behavior and hierarchy rather than forcing pixel identity across platforms. Report anything not tested or observable.

## 8. Hand off clearly

Summarize repository findings, changed behavior, reused or introduced contracts, validation results, and remaining limitations. Do not claim hidden or untested states are complete.

## Completion gate

Complete the Implement workflow only when the requested behavior and applicable states are implemented, repository conventions and shared impact are checked, relevant validation passes, and every deferred or unverified item is reported.
