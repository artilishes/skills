# Patterns, states, and responsive behavior

Use this reference to choose a starting structure and expose missing behavior. Adapt patterns to the product rather than treating them as templates.

## Contents

- Screen patterns
- State matrix
- Responsive behavior

## Screen patterns

### Dashboards

- Define the decisions the dashboard should enable.
- Establish scope, time range, freshness, and filters before metrics.
- Prioritize exceptions, changes, and actionable signals over decorative summaries.
- Connect summaries to underlying detail and follow-up actions.
- Avoid redundant metrics, unexplained charts, and equal-weight card walls.

### CRUD and administration

- Make object identity, status, ownership, and available actions easy to scan.
- Keep create, inspect, edit, archive, delete, restore, and bulk behavior consistent.
- Preserve filters, sorting, pagination, and selection when users return from detail work when practical.
- Show permission and lifecycle constraints near affected actions.
- Protect destructive and bulk operations with explicit scope and recovery.

### Data-heavy interfaces

- Prefer tables for exact comparison across repeated attributes.
- Keep headers, units, sorting, filters, selection, and row actions predictable.
- Support long values, missing values, many columns, large datasets, and partial failures.
- Use summaries or charts as navigation into detail, not replacements for inspectable data.
- Define virtualization, pagination, or incremental loading from data scale and interaction needs, not framework preference.

### Navigation

- Reflect the product's objects and user mental model.
- Keep global navigation distinct from local tabs, filters, and object actions.
- Show current location and preserve relevant scope.
- Use badges sparingly for actionable change or status.
- Collapse navigation responsively without removing critical destinations or context.

### Forms and settings

- Group fields by user decision, not storage schema.
- Use persistent labels, useful descriptions, sensible defaults, and clear required status.
- Validate at the earliest helpful moment without interrupting normal entry.
- Put errors next to affected controls and provide a summary when failures span a long form.
- Make save behavior, unsaved changes, dependencies, and dangerous settings explicit.

### Builders and editors

- Separate source material, work surface, selection, properties, and preview according to the task.
- Preserve selection and editing context while exposing advanced controls progressively.
- Make save or sync status, undo/redo, version state, validation, and publish state visible.
- Support empty canvases, invalid configurations, long-running generation, conflicts, and constrained viewports.
- Do not compress a multi-pane desktop editor into unusable narrow columns; transform panes into focused modes or staged views.

### Onboarding

- Move users toward first value, not feature awareness.
- Ask only for information required for the next useful step.
- Show progress when sequence or effort warrants it.
- Allow safe exit and return; preserve completed work.
- End with a meaningful product state and next action, not a dead-end success screen.

## State matrix

Specify presentation, available actions, accessibility, and recovery for applicable states:

| State | Questions to answer |
| --- | --- |
| Initial loading | What structure can appear immediately? Is progress determinate? Can the user leave or cancel? |
| Refreshing | Can existing data remain visible? How is staleness communicated? |
| Empty: first use | What is this area for, and what safe first action creates value? |
| Empty: no results | Which filter or query caused it, and how can the user broaden or clear it? |
| Empty: unavailable | Is data absent, delayed, restricted, or not applicable? |
| Partial data | Which regions succeeded or failed? Can the user act on available data? |
| Error | What failed, what was preserved, and what recovery is available? |
| Invalid input | Which field or rule failed, why, and where should focus move? |
| Disabled | Is the reason obvious or explained? Is there a prerequisite or permission path? |
| Pending mutation | Is duplicate action prevented? Can the work be canceled or left running? |
| Success | What changed, where is it visible, and what is the next useful action? |
| Destructive action | What scope is affected? Can it be undone, restored, or confirmed safely? |
| Restricted | Is the missing capability due to role, plan, state, or policy? |
| Long content | Does text wrap, truncate with access to the full value, or change layout safely? |
| Overflow | What scrolls, pins, condenses, or becomes a focused view? |
| Concurrent change | How are stale data, conflicts, or overwritten edits handled? |
| Offline or interrupted | What remains usable, queued, preserved, or retryable? |

Differentiate empty states. A new user with no objects needs orientation and creation; a filtered list with no matches needs filter recovery; an unavailable dataset needs explanation.

## Responsive behavior

Treat responsiveness as prioritization and transformation, not proportional shrinking.

### Wide layouts

Use available space for simultaneous context: persistent navigation, comparison columns, inspectors, or supporting detail. Limit line length and avoid stretching simple forms merely to fill width.

### Medium layouts

Reduce secondary context first. Collapse optional sidebars, condense action groups, and allow local regions to wrap while preserving the primary task and current scope.

### Narrow layouts

- Stack reading-order content.
- Convert side-by-side workspaces into focused modes when needed.
- Keep primary actions reachable without covering content.
- Move secondary actions into a clearly labeled menu.
- Provide an intentional pattern for wide data: priority columns, row detail, cards, or controlled horizontal scrolling.
- Avoid hover-only controls and tiny targets.
- Preserve labels and status meaning; icons alone rarely carry enough context.

### Responsive validation

Test more than named breakpoints. Check intermediate widths, text zoom, localization, keyboard overlays, long labels, dense data, expanded validation, and open menus or inspectors. Ensure the visual order matches the reading and focus order.
