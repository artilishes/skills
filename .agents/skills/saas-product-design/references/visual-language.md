# Visual language

Use visual treatment to communicate hierarchy, semantics, interaction, and change.

## Hierarchy

- Coordinate position, grouping, spacing, size, weight, and contrast rather than relying on font size alone.
- Reserve the strongest emphasis for the current task, decision, or exception.
- Use whitespace and alignment before adding dividers and containers. `[S10, S41]`
- Keep repeated structures stable enough to scan.
- Reduce secondary prominence without sacrificing contrast or legibility.

## Typography

- Define a small set of semantic roles and map them to the existing design system.
- Use readable sizes, line heights, and line lengths for the platform, density, and content.
- Adapt line height as size and measure change; do not force one percentage across roles. `[S31]`
- Use tabular numerals or aligned formatting when numeric comparison benefits.
- Preserve semantic heading order independently from visual size.
- Keep labels persistent; placeholder text is not a label. `[S45, G03]`

Font counts, golden-ratio scales, fixed opacity ranges, negative tracking values, and fluid-scaling equations are exploration recipes, not universal requirements. Prefer established tokens and verify at realistic widths, zoom, and localization. `[S10, S31, S41]`

## Color and themes

- Assign color by role: surfaces, text, borders, actions, focus, success, warning, danger, information, and data categories.
- Keep status meaning consistent across text, icons, controls, charts, and notifications.
- Pair important color meaning with text, iconography, pattern, or position.
- Use accent color selectively enough that action and status remain distinct.
- Treat light and dark themes as complete surface and contrast systems; do not directly invert values. `[S39, S48]`
- For categorical data, seek perceptual separation and verify contrast and distinguishability. Do not import fixed OKLCH or HSB increments without testing the actual palette and data. `[S48]`

Neutral-layer counts, 60-30-10 distributions, brightness deltas, saturation shifts, and brand-color overrides remain contextual.

## Components, geometry, and icons

- Keep radius, spacing, stroke, fill, icon style, and state behavior coherent across components with the same responsibility.
- Use one icon family or deliberately compatible families. Match detail, stroke, fill, and optical size to context.
- Prefer a label when an icon is unfamiliar, consequential, or ambiguous.
- Distinguish buttons, status chips, tags, fields, and static containers through behavior and semantics—not only geometry.
- Calculate nested geometry when it improves visual alignment, but do not force a radius subtraction or padding ratio that conflicts with tokens, touch size, or content. `[S41, S45]`

## Data visualization

- Choose a chart only when visual shape, distribution, relationship, or composition helps the task more than exact values alone.
- Keep title, labels, units, scale, time range, baseline, filters, comparison context, and missing-data meaning available when relevant.
- Avoid decorative charts that duplicate a percentage or cannot support interpretation or action. `[S35]`
- Curves, straight lines, fills, grids, axes, bars, and pie charts are contextual choices. Verify that the selected form preserves the data and the user's comparison task.

## Depth

- Use depth to explain layering, containment, selection, or interactivity.
- Keep elevation ordering coherent across menus, overlays, inspectors, and notifications.
- Avoid stacking borders, shadows, tints, blur, and rounded containers when spacing communicates the relationship.
- Do not universalize shadow multipliers, opacity ranges, or dark-mode shadow rules. `[S10]`

## Motion and feedback

- Use motion to explain continuity, hierarchy changes, progress, direct manipulation, or the relationship between trigger and result.
- Acknowledge input immediately, but do not animate unconfirmed success.
- Keep repeated-work transitions short and interruptible where appropriate.
- Preserve the final state without motion and respect reduced-motion preferences.
- Use standard easing and repository motion tokens unless a tested interaction requires otherwise.

Shimmer, particles, spring values, parallax, magnetic indicators, morphs, card tilts, hover reveals, and swipe choreography are contextual treatments. They are never evidence of product quality by themselves. `[S01, S12, S30]`

## Decision test

For each visual choice, ask:

1. What information, action, state, or relationship does it clarify?
2. Is the meaning preserved without color, hover, gesture, or animation?
3. Does it match the product's existing semantic system?
4. Does it survive realistic density, content variation, zoom, localization, narrow widths, and alternate themes?
5. Is this a durable rule, a product-specific decision, or a taste preference?

Remove a treatment when it cannot answer the first question.
