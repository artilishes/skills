# Patterns, states, and responsive behavior

Use this reference to expose missing product behavior. Adapt every pattern to the task and product evidence.

## Screen-pattern checks

### Dashboards

- Define the decisions and follow-up actions the dashboard should enable.
- Establish scope, time range, freshness, comparison baseline, and filters before interpreting metrics.
- Prioritize exceptions, changes, and actionable signals over decorative summaries.
- Connect summaries to evidence and relevant actions.
- Remove redundant metrics, controls, and charts. Do not assign equal weight to every widget.
- Choose each chart, table, list, status group, or timeline from the data question—not from the available grid space.

### CRUD and administration

- Make identity, status, ownership, lifecycle, and available actions easy to scan.
- Keep create, inspect, edit, archive, delete, restore, and bulk behavior consistent.
- Preserve useful list context—filters, sorting, pagination, selection, or scroll position—when users return from detail work.
- Show permission and lifecycle constraints near affected actions.
- State the scope and recovery path for destructive and bulk operations.

### Data-heavy interfaces

- Use stable headers, labels, units, formatting, sorting, filters, selection, and action placement.
- Right-align numeric columns when place-value comparison benefits; keep signs, units, and precision consistent.
- Preserve access to full values when content is truncated.
- Define missing, stale, unavailable, restricted, and partial values distinctly.
- Keep low-frequency row actions reachable without hover and predictable by keyboard and touch.
- Choose pagination, incremental loading, or virtualization from dataset size, task continuity, URL/state needs, and repository conventions—not fashion.

### Navigation

- Reflect product objects and user mental models.
- Distinguish global navigation from local tabs, filters, views, and object actions.
- Show current location and preserve relevant scope.
- Use badges only for meaningful status or actionable change.
- Collapse navigation without removing critical destinations or context.

### Forms and settings

- Group fields by user decision rather than storage schema.
- Use persistent labels, helpful examples, clear required status, and sensible defaults. `[S45]`
- Validate at the earliest useful moment without interrupting normal entry.
- Put field errors next to affected controls and summarize failures when a long form requires it.
- Make save behavior, unsaved changes, dependencies, and dangerous settings explicit.

### Builders and editors

- Separate source material, work surface, selection, properties, and preview according to the task.
- Preserve selection and editing context while disclosing advanced controls.
- Make save or sync status, undo/redo, version state, validation, conflicts, and publish state visible.
- Transform multi-pane desktop layouts into focused modes or staged views at narrow widths instead of compressing every pane.

### AI interfaces

- Show material prompt context, attached files, selected mode, and tool scope.
- Keep generation history when users need comparison, recovery, or reuse.
- Expose persistent memory for review, correction, and deletion when the system has it.
- Allow correction close to the generated artifact when inline editing preserves context.
- During meaningful latency, show truthful progress without fabricating internal reasoning or confidence.

### Gamified experiences

- Start with the user goal and define why progress or a reward helps it.
- Make progress and remaining effort legible.
- Use points, streaks, levels, public badges, competition, or social stakes only when they carry meaningful value for this audience.
- Do not replace product value with variable rewards, addictive friction removal, or performative engagement.

### Onboarding

- Move users toward first value rather than feature awareness.
- Ask only for information required for the next useful step.
- Use existing data to demonstrate value before asking for commitment when appropriate.
- Introduce the next important action in context; use a cue or checklist only when it reduces uncertainty.
- Allow safe exit and return, preserve completed work, and end in a meaningful product state.

## State matrix

For every applicable state, specify presentation, available actions, accessibility behavior, and recovery:

| State | Required decisions |
| --- | --- |
| Initial loading | What structure is known? Is progress determinate? Can the user leave or cancel? |
| Refreshing | Can existing data remain visible? How is staleness communicated? |
| Empty: first use | What is this area for, and what safe first action creates value? |
| Empty: no results | Which filter or query caused it, and how can it be changed or cleared? |
| Empty: unavailable | Is data absent, delayed, restricted, disconnected, or not applicable? |
| Partial data | Which regions succeeded or failed? Can users act on available data? |
| Error | What failed, what input or context was preserved, and what recovery is available? |
| Invalid input | Which field or rule failed, why, and where should focus move? |
| Disabled | Is the reason visible? Is there a prerequisite, permission, or plan path? |
| Pending mutation | Is duplicate action prevented? Can work be canceled or safely left running? |
| Success | What changed, where is it visible, and what is the next useful action? |
| Destructive action | What scope is affected? Is confirmation, undo, restore, or audit history appropriate? |
| Restricted | Is capability missing because of role, plan, object state, or policy? |
| Long content | Does content wrap, expand, truncate with full access, or change layout safely? |
| Overflow | What scrolls, pins, condenses, summarizes, or becomes a focused view? |
| Concurrent change | How are stale data, conflicts, merging, or overwritten edits handled? |
| Offline/interrupted | What remains usable, queued, preserved, or retryable? |

Do not collapse distinct empty states into one illustration and message.

## Responsive transformations

Treat responsiveness as reprioritization plus input adaptation.

### Wide

Use simultaneous context when it improves the task: navigation, comparison columns, an inspector, supporting detail, or multiple coordinated panes. Do not stretch a simple form merely to fill space.

### Medium

Remove secondary simultaneity first. Collapse optional panels, condense low-frequency actions, allow regions to wrap, and preserve the primary task and scope.

### Narrow and touch

- Stack content in reading order.
- Convert side-by-side workspaces into focused modes when comprehension requires it.
- Keep frequent actions reachable without covering content.
- Move secondary actions into a labeled menu.
- Provide an intentional wide-data strategy: priority columns, row detail, cards, summaries, or controlled horizontal scrolling.
- Use bottom sheets or other contextual surfaces only when they fit the platform and task; they are not mandatory.
- Treat swipe, long press, and edge gestures as accelerators with visible alternatives.
- Preserve labels and status meaning; do not depend on icons or color alone.

### Responsive validation

Test intermediate widths, zoom, text expansion, localization, keyboard overlays, long labels, dense data, open validation, menus, and inspectors. Ensure visual order matches reading and focus order.
