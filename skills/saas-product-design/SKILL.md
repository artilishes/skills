---
name: saas-product-design
description: Design, implement, refactor, and review SaaS product interfaces. Use for product requirements, screenshots, Figma designs, existing code, or partial implementations involving dashboards, CRUD/admin, data-heavy tools, navigation, forms/settings, builders/editors, onboarding, interface states, or responsive behavior. Excludes marketing sites, landing pages, and brand identity.
---

# SaaS Product Design

Ground every decision in user tasks, data, risk, frequency, and repository evidence before applying visual style.

## Choose a workflow

- **Design**: Read [design-workflow.md](references/design-workflow.md).
- **Implement**: Read [implementation-workflow.md](references/implementation-workflow.md) before changing code. Inspect the repository and its design system, then map decisions to local conventions.
- **Review**: Read [review-workflow.md](references/review-workflow.md). Keep every claim within what the supplied artifact can prove and identify missing evidence separately.
- **Hybrid work**: Run Review before Implement when improving an existing interface. Run Design before Implement when requirements do not yet define the interaction model.

Load supporting references selectively:

- Read [product-interface-principles.md](references/product-interface-principles.md) when hierarchy, flows, disclosure, action priority, density, or component boundaries require judgment.
- Read [patterns-states-responsive.md](references/patterns-states-responsive.md) when specifying a concrete screen, state coverage, overflow, or responsive transformations.
- Read [visual-language.md](references/visual-language.md) only when typography, color, depth, motion, or feedback is in scope. Preserve its distinction between durable principles and contextual preferences.
- Read [source-notes.md](references/source-notes.md) only when provenance matters or when extending this skill.

## Work from evidence

1. Identify the product outcome, primary users, recurring tasks, entities, permissions, risks, and success signal.
2. Inventory the available evidence: requirements, data shape, screenshots, design files, code, components, tokens, tests, analytics, and established conventions.
3. State material assumptions and unknowns. Continue with reversible assumptions when safe; ask only when an unknown would change the product model or create meaningful risk.
4. Model the happy path and important alternate paths before arranging components.
5. Define or evaluate hierarchy, interaction behavior, ownership, states, responsive behavior, accessibility, and feedback.
6. Prefer the simplest structure that keeps frequent work visible and makes infrequent or advanced work discoverable.
7. Verify the result against realistic content, failure cases, permissions, narrow viewports, keyboard use, and the existing system.

## Preserve product logic

- Begin with tasks and data; treat visual trends as optional styling.
- Keep the primary task and current context obvious. Make secondary actions quieter without making them undiscoverable.
- Keep required information and common actions visible; disclose rare, advanced, or conditional controls.
- Give each component one clear responsibility and keep state ownership explicit.
- Reuse existing patterns when they work. Introduce a new pattern only for a real behavior or information need.
- Treat loading, empty, error, disabled, success, permissions, long content, overflow, and responsive behavior as part of the feature.
- Use color, depth, and motion only to communicate semantics and change.
- Preserve accessibility and user control, including focus, labels, contrast, reduced motion, and recoverable destructive actions.

## Match the output to the workflow

For **Design**, return:

1. Product goal, users, assumptions, and key tasks
2. Screen structure and information hierarchy
3. Interaction model and navigation
4. Component responsibilities
5. State and edge-case matrix
6. Responsive behavior
7. Accessibility and acceptance criteria

For **Implement**, return or perform:

1. Repository and design-system findings
2. A scoped implementation plan tied to existing conventions
3. The interface changes, including required states and responsive behavior
4. Proportional verification and any remaining gaps

For **Review**, return:

1. A concise overall assessment
2. Prioritized findings with evidence, user impact, and a concrete fix
3. Missing states or evidence
4. A recommended improvement order

Use the selected workflow reference's completion gate as the stopping condition. Make every review finding evidence-based, product-specific, and actionable.

## Boundaries

Keep the skill technology-agnostic. Translate guidance into the repository's own language and conventions. Exclude marketing websites, landing pages, brand identity, acquisition copy, and framework-specific implementation rules. Keep this skill text-only: SKILL.md, agent metadata, and references. Exclude scripts, generators, executable dependencies, screenshots, transcripts, and third-party media.
