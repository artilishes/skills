---
name: saas-product-design
description: Design, implement, refactor, or review SaaS product interfaces using technology-agnostic product design methods. Use for dashboards, CRUD and administration screens, data-heavy tools, navigation, forms, settings, builders, editors, onboarding, and their empty, loading, error, disabled, overflow, responsive, motion, and feedback states. Trigger when working from product requirements, screenshots, Figma designs, existing UI code, or partial implementations; do not use for marketing sites, landing pages, or brand identity work.
---

# SaaS Product Design

Turn product intent into usable product interfaces. Ground every decision in user tasks, data, risk, frequency, and repository evidence before applying visual style.

## Choose a workflow

- **Design**: Read [design-workflow.md](references/design-workflow.md), then the relevant principles and patterns.
- **Implement**: Read [implementation-workflow.md](references/implementation-workflow.md) before changing code. Inspect the repository and its design system; never assume a framework or component library.
- **Review**: Read [review-workflow.md](references/review-workflow.md). Review only what the supplied artifact can prove and identify missing evidence separately.
- **Hybrid work**: Run Review before Implement when improving an existing interface. Run Design before Implement when requirements do not yet define the interaction model.

Load supporting references selectively:

- Use [product-interface-principles.md](references/product-interface-principles.md) for hierarchy, flows, disclosure, action priority, density, and component boundaries.
- Use [patterns-states-responsive.md](references/patterns-states-responsive.md) for screen patterns, state coverage, overflow, and responsive transformations.
- Use [visual-language.md](references/visual-language.md) for typography, color, depth, motion, and feedback. Preserve its distinction between durable principles and contextual preferences.
- Use [source-notes.md](references/source-notes.md) only when provenance matters or when extending this skill.

## Work from evidence

1. Identify the product outcome, primary users, recurring tasks, entities, permissions, risks, and success signal.
2. Inventory the available evidence: requirements, data shape, screenshots, design files, code, components, tokens, tests, analytics, and established conventions.
3. State material assumptions and unknowns. Continue with reversible assumptions when safe; ask only when an unknown would change the product model or create meaningful risk.
4. Model the happy path and important alternate paths before arranging components.
5. Define or evaluate hierarchy, interaction behavior, ownership, states, responsive behavior, accessibility, and feedback.
6. Prefer the simplest structure that keeps frequent work visible and makes infrequent or advanced work discoverable.
7. Verify the result against realistic content, failure cases, permissions, narrow viewports, keyboard use, and the existing system.

## Preserve product logic

- Let tasks and data determine the interface. Do not begin from a fashionable dashboard composition.
- Keep the primary task and current context obvious. Make secondary actions quieter without making them undiscoverable.
- Use progressive disclosure to manage complexity, not to hide required information or common actions.
- Give each component one clear responsibility and keep state ownership explicit.
- Reuse existing patterns when they work. Introduce a new pattern only for a real behavior or information need.
- Treat loading, empty, error, disabled, success, permissions, long content, overflow, and responsive behavior as part of the feature.
- Use color, depth, and motion to communicate semantics and change. Do not use them as decoration that competes with the task.
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

Avoid generic praise, aesthetic scoring without product context, framework-specific prescriptions, and exhaustive checklists that do not change the outcome.

## Boundaries

Keep the skill technology-agnostic. Translate guidance into the repository's own language and conventions. Exclude marketing websites, landing pages, brand identity, acquisition copy, and framework-specific implementation rules. Do not add scripts, generators, opaque dependencies, screenshots, transcripts, or third-party media to this skill.
