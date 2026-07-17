# Product-interface principles

Use these rules for product decisions. Treat them as context-sensitive operating principles rather than universal visual recipes.

## Start from intent, work, and data

- Identify the decision or repeated action the screen must support before selecting components.
- Show information because it enables monitoring, comparison, diagnosis, or action—not because dashboards traditionally contain metrics and cards.
- Choose the representation from the question users need to answer:
  - Exact lookup and repeated comparison usually favor a table or structured list.
  - Change over time may favor a chart when shape matters and a comparison value when magnitude matters.
  - Sequence or causality may favor a timeline.
  - A guided recap may use chapters or a story, but provide faster access when users also need quick lookup.
  - A summary must lead to inspectable detail when users need evidence or action.
- Keep scope, filters, freshness, units, precision, signs, baselines, and missing-value meaning visible when they affect interpretation.
- Align comparable numbers consistently. Use compact status treatments only with explicit text and non-color meaning.

## Establish hierarchy before decoration

Describe the reading order in plain language:

1. Current location and scope
2. Primary status, exception, or decision
3. Main work surface
4. Frequent action
5. Secondary detail and utilities

Use position, grouping, spacing, type roles, and contrast to produce that order. Add a container only when it communicates ownership, interaction, or grouping that spacing cannot. Avoid equal-weight card walls and duplicate controls.

## Design flows and state transitions

Model entry, prerequisites, user action, system response, success, failure, recovery, and next useful action. Cover first use and return use, create and edit, valid and invalid input, available and unavailable data, authorized and restricted access, and safe and destructive changes.

Do not use a wizard merely to make a form feel designed. Use steps when order, dependencies, validation boundaries, effort, or progress genuinely matter.

## Disclose complexity deliberately

Keep frequent, required, or decision-critical information and controls visible. Defer advanced, rare, or conditional controls behind a labeled and predictable disclosure. Preserve values and errors when content collapses.

Never use disclosure to hide:

- The primary action or current status
- Destructive scope or consequences
- Information required to decide whether to proceed
- The only path to an action

Hover, swipe, long press, keyboard shortcuts, and drag-and-drop may accelerate work. Provide a visible, keyboard-accessible, and touch-accessible alternative for essential behavior. Tooltips may clarify an unfamiliar control; they do not repair a missing label or inaccessible action.

## Choose an interaction surface from responsibility

- Use **inline interaction** for small changes that benefit from surrounding context.
- Use a **popover** for lightweight choices or supporting information anchored to a trigger.
- Use a **modal** for bounded work that must interrupt the current context.
- Use a **drawer or inspector** for contextual detail that should coexist with a list, canvas, or selection.
- Use a **page or focused workspace** for complex, long, deep-linkable, collaborative, or high-risk work.

These are decision heuristics, not component mandates. Avoid nested overlays, preserve focus, and provide a clear close, cancel, or completion path.

## Prioritize and name actions

- Make the primary mutation obvious within its decision context.
- Place frequent object actions near the object they affect.
- Group low-frequency actions without hiding destructive consequences.
- Distinguish navigation from mutation, preview from commit, and draft from publish.
- Prevent duplicate submissions while a mutation is pending.
- Prefer undo for common reversible actions; use confirmation when consequences are severe, broad, or difficult to reverse.

Use specific action labels. Do not rely on a generic arrow, magic icon, or color change to communicate consequence.

## Give every change accurate feedback

Acknowledge input, expose pending work, confirm completion, and make failure recoverable near the affected context. Use a global notification only for background or cross-screen events. Persistent conditions such as unsaved, offline, failed, or restricted work need persistent status.

Motion may show continuity between a trigger and a result, but it must not delay repeated work or imply success before confirmation.

Use optimistic feedback only when failure is uncommon, the change is reversible, and rollback or reconciliation is clear. Otherwise show a truthful pending state.

## Maintain trust

- Show destructive scope and consequences.
- Distinguish draft, saved, synced, published, pending, and failed states.
- Explain disabled or restricted actions when the reason helps users proceed.
- Preserve input across recoverable errors.
- Make automated or AI-generated output identifiable, reviewable, and correctable.
- If AI uses context, files, memory, tools, or prior history, make material inputs and persistent memory inspectable and manageable when applicable.

## Scale systems to the product

Reuse stable contracts for repeated behaviors, states, and semantics. Do not create a highly configurable abstraction merely to remove visual duplication. Add tokens, variants, and shared components in proportion to repetition, product complexity, and team needs.

## Preserve accessibility and user control

Use semantic controls, meaningful names, logical headings, visible focus, keyboard access, sufficient contrast, programmatic errors, non-color status cues, and predictable focus movement. Respect zoom, text expansion, reduced motion, localization, and alternate input methods.
