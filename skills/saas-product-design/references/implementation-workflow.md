# Implementation workflow

Use this workflow before implementing or refactoring a SaaS interface in an existing repository.

## Contents

1. Inspect before proposing
2. Reconstruct the current product model
3. Map the design to local primitives
4. Plan the smallest coherent change
5. Implement in behavioral layers
6. Preserve system integrity
7. Verify proportionally
8. Hand off clearly

## 1. Inspect before proposing

Find the repository's actual conventions:

- Application structure and routing
- Existing screens that solve similar problems
- Design tokens, themes, typography, spacing, and layout primitives
- Reusable components and their supported variants
- Form, validation, table, chart, overlay, notification, and navigation patterns
- Data contracts, permissions, loading behavior, and error handling
- Accessibility utilities and keyboard conventions
- Responsive conventions and supported viewports
- Tests, stories, fixtures, preview tools, and validation commands

Read component implementations when their behavior is unclear. Do not infer capabilities from names alone. Confirm whether a visual inconsistency is intentional, legacy, or accidental before replacing it.

## 2. Reconstruct the current product model

Trace:

- Entry point and route context
- Data source and lifecycle
- User role and permitted actions
- Main task and completion signal
- Current state ownership
- Existing edge-state behavior
- Dependencies shared with other screens

For a refactor, distinguish behavioral changes from structural or visual cleanup. Preserve working behavior unless the requested change explicitly alters it.

## 3. Map the design to local primitives

Create a small mapping before writing code:

| Need | Existing pattern | Decision |
| --- | --- | --- |
| Page shell | Local shell or layout | Reuse, extend, or justify a new pattern |
| Primary action | Existing action hierarchy | Match established priority and behavior |
| Data display | Table, list, cards, chart | Choose from task and data shape |
| Edit flow | Inline, overlay, page | Match complexity, risk, and deep-link needs |
| Feedback | Local status or notification pattern | Cover pending, success, and failure |
| Responsive behavior | Existing breakpoint behavior | Extend without one-off assumptions |

Prefer composition over duplicating a near-identical component. Extend a shared component only when the new behavior belongs to all consumers; otherwise keep the variation local.

## 4. Plan the smallest coherent change

Define:

- Files and components in scope
- State and data changes
- New versus reused primitives
- Accessibility behavior
- Edge states
- Responsive transformations
- Tests or verification needed
- Explicit non-goals

Avoid broad design-system rewrites to solve one screen. If the current system cannot support a necessary behavior, introduce the smallest reusable addition and document why.

## 5. Implement in behavioral layers

Build in this order when practical:

1. Semantic structure and accessible names
2. Data flow, permissions, and state ownership
3. Primary task and action behavior
4. Validation, pending, success, failure, and recovery
5. Layout and responsive transformations
6. Visual hierarchy and system-aligned styling
7. Motion and secondary polish

Use realistic long labels, large values, empty collections, errors, and slow operations during implementation. A layout that works only with ideal fixture data is incomplete.

## 6. Preserve system integrity

- Reuse tokens instead of adding isolated values when equivalent semantics exist.
- Keep action, status, and navigation language consistent with the product.
- Avoid embedding business rules in visual-only components.
- Keep destructive actions explicit and recoverable where possible.
- Preserve focus across overlays, navigation, async updates, and validation failures.
- Avoid color-only status communication.
- Respect reduced-motion and input-method differences.
- Do not hide unavailable actions without explaining permission or prerequisite when that knowledge helps the user.

## 7. Verify proportionally

Use the repository's own verification path. Check at minimum:

- Primary and alternate flows
- Loading, empty, error, disabled, success, and permission states
- Validation and destructive actions
- Narrow and wide layouts
- Long text, large data, and overflow
- Keyboard order, focus visibility, labels, and announcements
- Existing consumers of changed shared components
- Relevant automated checks

For visual verification, compare hierarchy and behavior rather than forcing pixel identity across platforms. Report what was verified, what could not be verified, and why.

## 8. Hand off clearly

Summarize repository findings, changed behavior, reused or introduced patterns, verification results, and remaining limitations. Do not claim hidden or untested states are complete.
