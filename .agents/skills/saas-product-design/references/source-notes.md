# Research and attribution notes

This skill combines independently paraphrased lessons from selected public videos by Kole Jain with separately identified accessibility, risk, repository, and verification guardrails. It does not contain transcripts, copied passages, screenshots, Figma assets, video assets, or an implied endorsement by the creator.

## Research method

The supplied NotebookLM corpus contained 51 selected sources: 49 unique videos, one duplicate of the dashboard-flaws video, and the channel catalog.

The reconstruction used four passes:

1. Inventory every unique video and classify it as high relevance, partial relevance, or out of scope for technology-agnostic SaaS product interfaces.
2. Audit all 19 high-relevance videos independently, in source order, separating source-explicit lessons from agent-derived operational rules.
3. Audit four partial sources that could add distinct product behavior: dashboard motion, data storytelling, gamification, and TikTok interaction patterns.
4. Exclude the remaining partial sources when their transferable lessons duplicated the high-relevance set or depended mainly on marketing layouts, visual trends, or tool-specific execution.

NotebookLM citations were inspected during research but are not portable outside the notebook. Detailed source-level provenance and evidence mapping are maintained privately and are intentionally excluded from this repository and the distributable skill.

## Attribution boundary

The following are source-informed directions:

- Let user intent, tasks, and data shape the interface.
- Design flows, alternate states, feedback, and recovery.
- Apply progressive disclosure without losing discoverability.
- Match representations and interaction surfaces to their actual responsibility.
- Adapt mobile and desktop interactions to platform context.
- Use coherent hierarchy, components, semantic color, themes, and feedback.
- Treat design-system scale, AI transparency, onboarding, and gamification as product decisions rather than decoration.

The following are independent guardrails added by this skill and must not be attributed to the videos without consulting the private provenance record:

- Repository inspection and shared-component impact analysis
- Semantic HTML and programmatic accessibility requirements
- Keyboard, touch, focus-management, reduced-motion, and non-color fallbacks
- Permission, validation, destructive-action, rollback, and reconciliation safeguards
- Review evidence boundaries, severity ranking, automated checks, and implementation handoff requirements

## Interpretation rules

- A source-explicit recommendation is evidence of what the video teaches, not proof that the recommendation is universally correct.
- An agent-derived operational rule must preserve the source's problem and limits; it must not promote the demonstrated component or number into a default.
- A repeated lesson across sources increases confidence in the direction, not in an exact visual recipe.
- Any lesson requiring the on-screen example remains contextual unless the visual artifact is reviewed directly.
- Accessibility, risk, platform, and repository evidence can override source advice.

When extending this skill, update the private provenance record first. Do not add an operational rule without declaring whether it is source-supported, independently guarded, contextual, or excluded.
