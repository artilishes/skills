# Design workflow

Use this workflow to turn product requirements into a screen or connected product flow.

## Contents

1. Frame the product problem
2. Model tasks and flows
3. Define screen anatomy
4. Establish information hierarchy
5. Define the interaction model
6. Assign component responsibilities
7. Specify states and responsive behavior
8. Deliver a screen specification
9. Apply the completion gate

## 1. Frame the product problem

Capture only the facts that affect the interface:

- Product outcome and user outcome
- Primary and secondary user roles
- Jobs users perform, ordered by frequency and importance
- Core entities, relationships, status changes, and permissions
- High-risk or irreversible actions
- Data volume, variability, freshness, and latency
- Desktop, mobile, embedded, or constrained operating contexts
- Existing product or design-system constraints

Separate facts from assumptions. Resolve ambiguity when it changes navigation, data ownership, permissions, or the primary task. Otherwise make the smallest reversible assumption and label it.

## 2. Model tasks and flows

Describe the main path as a sequence of user decisions and system responses. Include entry points, prerequisite context, save or submit behavior, success confirmation, recovery, and the next useful action.

Add alternate paths for:

- First use versus returning use
- Create versus edit
- Valid versus invalid input
- Available versus unavailable data
- Authorized versus restricted access
- Single-item versus bulk work
- Immediate versus long-running operations
- Safe versus destructive changes

Do not use a modal, drawer, wizard, or separate page until the task model justifies it.

## 3. Define screen anatomy

Organize the screen into responsibilities rather than visual rectangles:

1. **Context**: Where am I and what object or scope am I viewing?
2. **Orientation**: What is the current state, time range, filter, or selection?
3. **Primary work**: What information or control enables the main task?
4. **Actions**: What can I do now, and which action matters most?
5. **Support**: What explanation, history, metadata, or help is needed?
6. **System feedback**: What is loading, saved, failed, blocked, or complete?

Order regions by user priority, not by component popularity. Keep the primary object and action visible without forcing users to infer them from decoration.

## 4. Establish information hierarchy

- Lead with the screen purpose and current scope.
- Put decision-making information before supporting detail.
- Group related controls with the content they affect.
- Keep labels specific and stable across navigation, headings, actions, and feedback.
- Use spacing and alignment before adding borders, containers, or color.
- Allow dense interfaces when comparison and repeated work benefit from density.
- Avoid equal visual weight for every metric, card, action, or setting.

Describe the hierarchy in words before specifying visual treatment. If the hierarchy cannot be explained clearly, the screen is not ready for styling.

## 5. Define the interaction model

Specify:

- Navigation level and persistent context
- Selection behavior and keyboard expectations
- Filters, search, sorting, pagination, and saved views
- Create, edit, duplicate, archive, delete, restore, and bulk actions
- Autosave, explicit save, draft, publish, or apply behavior
- Inline, overlay, or full-page transitions
- Undo, confirmation, and recovery behavior
- Progress and completion feedback for long-running work

Prefer in-place interactions for small, low-risk edits with sufficient context. Prefer a separate page or focused workspace for complex, deep-linkable, multi-step, or high-risk work. Use overlays for bounded tasks that benefit from retaining the underlying context.

## 6. Assign component responsibilities

For each component, define:

- Information displayed
- User action accepted
- State owned versus received
- Validation or business rule enforced
- Feedback emitted
- Behavior when content is missing, long, delayed, or restricted
- Responsive transformation

Split components by coherent behavior and ownership, not arbitrary visual fragments. Keep cross-screen business rules outside purely presentational components in whatever architecture the repository uses.

## 7. Specify states and responsive behavior

Create a state matrix using [patterns-states-responsive.md](patterns-states-responsive.md). Include states that change layout, available actions, copy, or recovery—not merely a generic note that states exist.

Define responsive behavior by priority:

- What remains visible?
- What wraps, stacks, condenses, scrolls, summarizes, or moves behind disclosure?
- Which controls need a mobile-specific interaction?
- How are wide tables, builders, inspectors, and sidebars handled?
- What minimum content width preserves comprehension?

## 8. Deliver a screen specification

Use this compact format:

```text
Screen: [name]
Goal: [user outcome]
Entry points: [where users come from]
Primary task: [task]

Structure:
1. [region] — [purpose and priority]

Interactions:
- [trigger] -> [system response] -> [feedback/recovery]

Components:
- [component] — owns [responsibility]; handles [states]

States:
- [state] — [presentation, available actions, recovery]

Responsive:
- Wide / medium / narrow transformations

Acceptance criteria:
- Observable behavior, accessibility, and edge cases
```

Keep the specification behavioral. Add measurements only when a platform, design system, or artifact supplies them.

## 9. Completion gate

Complete the Design workflow only when the specification covers the product goal, primary and alternate paths, screen structure, interactions, component ownership, every applicable state, wide/medium/narrow behavior, accessibility, and observable acceptance criteria; label every unresolved assumption.
