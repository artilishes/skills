# Review workflow

Use this workflow to review screenshots, Figma designs, existing code, or partially implemented SaaS interfaces.

## 1. Set the evidence boundary

Identify what the artifact can prove:

- **Screenshot**: visible hierarchy, density, alignment, labeling, contrast clues, and one captured state
- **Design file**: structure, variants, tokens, component reuse, prototypes, and defined responsive behavior
- **Code**: semantics, state coverage, component boundaries, interaction logic, accessibility implementation, and responsiveness
- **Running interface**: actual interactions, focus, timing, overflow, state transitions, and viewport behavior
- **Requirements**: intended users, tasks, rules, and success criteria

Do not infer working behavior from a static image. Do not infer visual quality from code alone. List important missing evidence as a review finding or limitation.

## 2. Reconstruct intent

State the likely screen goal, primary user, primary task, core object, and current state. If these are not clear from the artifact, flag that ambiguity before critiquing polish.

Evaluate in this order:

1. Product and task fit
2. Information architecture and hierarchy
3. Interaction model and action priority
4. State, feedback, recovery, and permissions
5. Responsive and overflow behavior
6. Accessibility
7. Consistency and component reuse
8. Visual language and motion

Do not let attractive styling offset a broken task flow.

## 3. Prioritize findings

Use four levels:

- **Critical**: Prevents task completion, creates data loss or dangerous action, blocks accessibility, or exposes users to severe misunderstanding.
- **High**: Causes frequent confusion, hides a primary action, breaks an important state or viewport, or creates substantial rework.
- **Medium**: Slows comprehension, weakens consistency, or mishandles a meaningful but recoverable case.
- **Low**: Improves polish, clarity, or consistency without materially blocking the task.

Prioritize by user impact, frequency, risk, and confidence—not by how easy a fix is or how visually noticeable it appears.

## 4. Make each finding actionable

Write each finding with:

```text
[Priority] Short finding title
Evidence: What is visible or traceable in the artifact.
Impact: Which user or task is affected and how.
Recommendation: A concrete behavioral or structural change.
Verification: How to know the change worked.
```

Reference a specific region, state, component, or code location. Avoid findings such as "improve hierarchy" or "make it cleaner" without explaining what should become more or less prominent and why.

## 5. Review by modality

### Screenshots

- Inspect visible task hierarchy, grouping, density, action placement, labels, status clarity, and overflow clues.
- Ask for or identify missing loading, empty, error, validation, expanded, disabled, and narrow states.
- Phrase interaction and accessibility concerns as unverified unless visible evidence supports them.

### Figma or other design files

- Inspect frame hierarchy, component instances, variants, variables or styles, constraints, prototype connections, and content realism.
- Check whether states are designed as behaviorally distinct variants rather than disconnected visual copies.
- Verify responsive intent from constraints and representative frames; do not assume desktop frames will collapse correctly.

### Code

- Trace rendered states and interaction paths, not only component names.
- Check semantics, labels, keyboard behavior, focus, validation, async feedback, permissions, overflow, and shared-component impact.
- Distinguish product-design issues from implementation defects.
- Attach file and line references when supported by the review environment.

### Partial implementations

- Separate incomplete-by-scope work from regressions or design gaps.
- Identify the smallest sequence that makes the primary flow coherent before requesting polish.

## 6. Report in improvement order

Return:

1. **Assessment**: two or three sentences on task clarity and major risk
2. **Findings**: ordered Critical to Low
3. **Missing states or evidence**: what cannot yet be evaluated
4. **Improvement sequence**: the fewest coherent passes, such as flow → states → responsiveness → polish

Mention strengths only when they should be preserved during changes. Do not pad the review with generic compliments or restate every visible detail.
