# Product interface principles

Apply these principles across SaaS screens. Adapt them to user goals, domain risk, platform conventions, and the existing product system.

## Let work and data shape the screen

- Start from user decisions, repeated actions, and data relationships.
- Show data because it supports monitoring, comparison, diagnosis, or action—not because dashboards traditionally contain cards or charts.
- Match representation to the task: exact lookup favors tables or lists; trend detection may favor charts; status scanning may favor grouped summaries.
- Keep provenance, freshness, units, time ranges, filters, and missing-data meaning visible when they affect interpretation.
- Place actions near the object or state they change.

## Build an explicit hierarchy

Give the interface a clear reading order:

1. Current location and scope
2. Primary status or decision
3. Main work surface
4. Primary action
5. Secondary detail and utilities

Use position, grouping, whitespace, typography, and contrast before adding containers. Avoid card grids where every item receives equal emphasis regardless of importance.

## Design flows, not isolated screens

Account for entry, progress, completion, recovery, and return. Preserve context across steps where it reduces memory load. Provide a clear next action after creation, import, approval, or setup.

Prefer fewer decisions at once, but do not split a simple task into a ceremonial wizard. Use steps when order, validation boundaries, dependencies, or progress visibility provide real value.

## Apply progressive disclosure deliberately

Keep frequent and required controls visible. Defer advanced, rare, or conditional options behind a clearly labeled disclosure. Preserve current values and validation when content is collapsed.

Do not use disclosure to conceal primary actions, critical status, destructive consequences, or information users need to decide whether to proceed.

## Choose the right interaction surface

- Use **inline interaction** for small changes that benefit from surrounding context.
- Use a **popover** for lightweight choices or supporting information anchored to a trigger.
- Use a **modal** for bounded work that must interrupt the current flow and can be completed without broader navigation.
- Use a **drawer or inspector** for contextual detail that should coexist with a list, canvas, or selection.
- Use a **page or focused workspace** for complex, long, deep-linkable, collaborative, or high-risk tasks.

Avoid nesting overlays. Preserve focus and provide a clear close or completion path.

## Prioritize actions

- Use one dominant action per decision context, not one per container.
- Keep frequent object actions close to the object.
- Group low-frequency actions without hiding destructive consequences.
- Distinguish navigation from mutation and preview from commit.
- Make pending actions resistant to duplicate submission.
- Use confirmation when consequences are severe or hard to reverse; prefer undo for common reversible actions.

## Give components coherent responsibilities

Define components by behavior and information ownership. A component should make clear what it displays, changes, validates, and reports. Avoid components that silently fetch unrelated data, mutate distant state, or combine several independent workflows merely because they share a visual box.

Use shared components for stable repeated contracts. Do not force different behaviors into one highly configurable abstraction solely to remove visual duplication.

## Make system status visible

Communicate what the system is doing, what changed, whether the action succeeded, and what the user can do next. Keep feedback near the affected context when possible. Use global notifications for cross-screen or background events, not as a substitute for field or section-level feedback.

## Design for density and scanning

Density is contextual. Favor compact layouts for repeated comparison and expert operations; favor more guidance and separation for infrequent, risky, or novice tasks. Support scanning with aligned columns, stable labels, meaningful grouping, and predictable action placement.

Do not solve density by shrinking text or touch targets beyond usability. Offer column controls, filters, summaries, or disclosure when the data genuinely exceeds the available space.

## Maintain user trust

- Show destructive scope and consequences.
- Distinguish draft, saved, synced, published, and failed states.
- Explain disabled or restricted actions when the reason is useful.
- Preserve user input across recoverable errors.
- Avoid optimistic feedback when failure would be costly or misleading.
- Make automated or AI-generated output identifiable, reviewable, and correctable when applicable.

## Preserve accessibility

Use semantic controls, meaningful names, logical heading order, visible focus, sufficient contrast, keyboard access, non-color status cues, and programmatic error relationships. Manage focus when content appears, disappears, or changes context. Respect zoom, text expansion, reduced motion, and alternate input methods.
