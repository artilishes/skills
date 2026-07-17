# Visual language

Use visual treatment to explain hierarchy, semantics, interaction, and change. Separate durable interface principles from contextual stylistic preferences.

## Durable principles

### Hierarchy

- Create emphasis through a coordinated system of position, spacing, size, weight, and contrast.
- Reserve the strongest emphasis for the current task, decision, or exceptional state.
- Use alignment and whitespace to show relationships before adding dividers or containers.
- Keep repeated structures visually stable so users can scan rather than relearn.
- Reduce the prominence of metadata and secondary actions without making them illegible.

### Color

- Assign color by semantic role: surface, text, border, action, focus, success, warning, danger, and information.
- Keep status meaning consistent across text, icons, controls, charts, and notifications.
- Pair color with labels, icons, patterns, or position when status matters.
- Meet the applicable contrast needs for text, controls, focus, disabled content, and data visualization.
- Use brand or accent color selectively so action and status remain legible.
- Treat dark mode as a complete surface and contrast system, not an inversion filter.

### Depth

- Use depth to explain layering, containment, selection, or interactivity.
- Keep elevation ordering consistent across menus, overlays, inspectors, and notifications.
- Avoid stacking borders, shadows, tints, and rounded containers when spacing alone communicates the grouping.
- Ensure overlays remain distinguishable without disconnecting users from the underlying context.

### Typography

- Use readable sizes, line heights, and line lengths for the platform and density.
- Keep a small, systematic type hierarchy tied to roles rather than isolated values.
- Use tabular numerals or aligned formatting when numeric comparison benefits.
- Preserve semantic heading order independently from visual size.
- Avoid relying on placeholder text as a label or making secondary text too faint to read.

### Motion

- Use motion to explain continuity, hierarchy changes, progress, or direct manipulation.
- Keep feedback immediate and transitions short enough not to delay repeated work.
- Avoid motion that hides status, shifts targets unexpectedly, or implies completion before the system confirms it.
- Respect reduced-motion preferences and provide equivalent state cues without animation.

### Feedback

- Acknowledge input, show pending work, confirm completion, and expose failure near the affected context.
- Keep persistent status visible for persistent conditions; do not rely on a disappearing notification for unsaved, offline, or failed states.
- Use global notifications for background or cross-screen events and local feedback for local changes.
- Preserve user input and a recovery path when possible.

## Contextual preferences

Treat the following as stylistic options, never universal quality rules:

- Very rounded versus restrained corner radii
- Soft shadows, flat borders, tinted surfaces, or high-contrast panels
- Pure monochrome versus broader accent palettes
- Light, dark, or mixed surface themes
- Glass, blur, glow, gradient, or grain effects
- Spacious editorial layouts versus compact operational density
- Animated charts, counters, or decorative transitions
- Icon-forward controls versus text-forward controls

Adopt a preference only when it fits the product character, platform norms, existing design system, performance, accessibility, and task frequency. Do not introduce a fashionable treatment as evidence of product quality.

## Decision test

For each visual choice, ask:

1. What information or interaction does this treatment clarify?
2. Does it remain understandable without color, hover, or animation?
3. Is it consistent with similar roles elsewhere in the product?
4. Does it survive realistic density, long content, narrow widths, and alternate themes?
5. Is it a durable semantic rule or a contextual preference?

Keep durable rules stable. Allow preferences to vary only within a coherent system.
