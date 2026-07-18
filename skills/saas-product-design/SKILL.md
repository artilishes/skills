---
name: saas-product-design
description: Design, implement, refactor, and review SaaS product interfaces. Use for product requirements, screenshots, Figma designs, existing code, or partial implementations involving dashboards, CRUD/admin, data-heavy tools, navigation, forms/settings, builders/editors, onboarding, AI interfaces, interface states, or responsive behavior. Excludes marketing sites, landing pages, portfolios, and brand identity.
---

# SaaS Product Design

Design the product behavior before styling the surface. Ground decisions in user intent, tasks, data, risk, frequency, platform, and repository evidence.

## Select the workflow

- **Design**: Read [design-workflow.md](references/design-workflow.md).
- **Implement or refactor**: Read [implementation-workflow.md](references/implementation-workflow.md). Inspect the repository before proposing a design-system or component change.
- **Review**: Read [review-workflow.md](references/review-workflow.md). Separate visible evidence from unverified behavior.
- **Hybrid**: Review before changing an existing interface. Design before implementation when the interaction model is unresolved.

Load only the references needed for the task:

- [product-interface-principles.md](references/product-interface-principles.md) for hierarchy, data representation, disclosure, actions, feedback, and trust.
- [patterns-states-responsive.md](references/patterns-states-responsive.md) for screen patterns, state coverage, onboarding, platform behavior, and responsive transformations.
- [visual-language.md](references/visual-language.md) for typography, color, depth, icons, motion, and contextual visual recipes.
- [source-notes.md](references/source-notes.md) for the research method and attribution boundary.

## Apply the evidence hierarchy

Resolve conflicts in this order:

1. User goals, domain rules, permissions, and risk
2. Supplied requirements and observable product evidence
3. Existing repository contracts, components, tokens, and platform conventions
4. Accessibility, user control, and recovery guardrails
5. Durable principles supported by the research corpus
6. Contextual heuristics and visual preferences

Never override product evidence with a source recipe. Treat exact ratios, counts, color shifts, spacing grids, radii, shadows, chart styles, easing values, and component placements as hypotheses unless the product or design system already requires them.

## Build the product model

Before arranging components, identify:

- The user outcome and primary recurring task
- Core entities, relationships, statuses, and data types
- Entry points, current scope, and completion signal
- Roles, permissions, prerequisites, and destructive consequences
- Data volume, variability, freshness, latency, and missing-value meaning
- First-use, returning, loading, empty, error, restricted, pending, success, and recovery paths
- Wide, medium, narrow, keyboard, touch, and reduced-motion contexts

State consequential unknowns. Continue with a reversible assumption only when it does not change the product model or create meaningful risk.

## Calibrate specificity

- Distinguish **supplied facts**, **observations**, **assumptions**, and **proposals**. Never present a proposal as an established product rule.
- Do not invent product entities, fields, lifecycle states, information architecture, business rules, permission models, keyboard shortcuts, breakpoints, platform measurements, accessibility conformance targets, or backend contracts.
- Introduce an exact value only when it comes from supplied requirements, observable repository or platform evidence, or a clearly labeled proposal that must be tested.
- Default to a compact, implementation-ready answer. Include only decisions needed to resolve the requested product behavior; offer optional elaboration instead of fabricating completeness.
- When missing information would materially change the result, name the decision needed. Otherwise use the smallest reversible assumption and label it.

## Make product decisions

- Let the task and data determine the representation. Do not add cards, charts, timelines, chips, or dashboards by convention.
- Keep the primary context, status, and frequent action explicit. Disclose secondary or advanced controls without making them unreachable.
- Design connected flows and state transitions, not an isolated ideal screen.
- Choose inline interaction, popover, modal, drawer, page, or focused workspace from task scope, interruption, risk, and context needs.
- Give every action immediate and accurate feedback. Preserve user input and provide recovery when a request fails.
- Keep essential actions available without depending exclusively on hover, gesture, color, animation, or an unexplained icon.
- Transform responsive layouts by priority and input method; do not proportionally shrink a desktop composition.
- Reuse the existing system when it supports the behavior. Add a pattern only for a distinct information or interaction need.
- Use visual hierarchy, color, depth, and motion to communicate meaning and change. Treat decorative treatments as optional.

## Preserve independent guardrails

The research sources do not replace engineering and accessibility judgment. Always:

- Inspect actual component behavior, data contracts, shared consumers, and tests before implementation.
- Use semantic controls, accessible names, logical focus, keyboard access, sufficient contrast, non-color status cues, and reduced-motion support.
- Keep destructive scope explicit and recoverable where possible.
- Use optimistic feedback only when failure is uncommon, consequences are reversible, and rollback or reconciliation is clear.
- Verify realistic content, permissions, failures, overflow, localization, and supported viewports.
- Report what was not observable or tested instead of inferring completion.

## Complete the work

For **Design**, deliver a compact specification that separates supplied facts, assumptions, and proposals, then covers the product goal, task and flow model, screen structure, interaction decisions, component responsibilities, applicable states, responsive transformations, accessibility behavior, and observable acceptance criteria. Do not fill absent requirements with fictional detail.

For **Implement**, report repository findings, implement the smallest coherent change, cover applicable states and input methods, run proportional validation, and name remaining gaps.

For **Review**, return a concise assessment, missing states or evidence, and the smallest coherent improvement sequence. Every finding must use the exact fields **Priority**, **Evidence**, **Impact**, **Recommendation**, and **Verification**; omit a finding if the supplied artifact cannot support its evidence.

Use the selected workflow reference's completion gate. Do not stop at a polished default state.

## Boundaries

Keep the skill technology-agnostic and adapt it to the repository's language. Exclude marketing pages, acquisition copy, portfolios, brand identity, Figma/Webflow tutorials, and framework-specific implementation recipes. Do not reproduce transcripts, source assets, screenshots, or third-party media.
