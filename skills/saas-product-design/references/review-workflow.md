# Review workflow

This workflow combines source-supported product questions with an independent evidence boundary. Review only what the supplied artifacts can prove.

## 1. Declare the evidence boundary

- **Requirements** establish intended users, tasks, rules, and success criteria.
- **Screenshot** shows visible hierarchy, density, grouping, labels, contrast clues, and one captured state.
- **Design file** may show structure, components, variants, tokens, prototypes, and responsive intent.
- **Code** may show semantics, rendered states, ownership, interaction logic, accessibility implementation, and responsive rules.
- **Running interface** can demonstrate interaction, focus, timing, overflow, state transitions, and viewport behavior.

Do not infer working behavior from a static image or visual quality from code alone. List missing evidence separately.

## 2. Reconstruct intent before critique

State the likely product outcome, user, recurring task, core object, current scope, and captured state. If these are unclear, flag the ambiguity before reviewing polish.

Evaluate in this order:

1. Task and data fit
2. Flow and state completeness
3. Hierarchy, disclosure, and action priority
4. Feedback, recovery, permissions, and trust
5. Responsive and input-method behavior
6. Accessibility
7. Component and system coherence
8. Visual language and motion

Do not let attractive styling offset a broken task flow.

## 3. Review by artifact

### Screenshot

Inspect visible reading order, task prominence, grouping, density, labels, action placement, status clarity, data context, and overflow clues. Phrase interaction, keyboard, semantics, and hidden-state concerns as unverified unless other evidence supports them.

### Design file

Inspect frame structure, component instances, variants, variables, constraints, prototype connections, realistic content, and state coverage. Check whether states are behaviorally distinct and whether responsive transformations are actually defined.

### Code

Trace rendered states and action paths. Check semantics, names, keyboard behavior, focus, validation, async feedback, permissions, overflow, and shared-component impact. Distinguish product-design issues from implementation defects and cite file locations when available.

### Running interface

Exercise the primary path and representative alternate states. Test narrow and intermediate widths, keyboard use, long content, slow operations, errors, permissions, menus, overlays, and recovery.

## 4. Prioritize by impact

- **Critical**: Prevents completion, creates data loss or dangerous mutation, blocks essential accessibility, or causes severe misunderstanding.
- **High**: Frequently hides or breaks an important task, state, permission, or viewport.
- **Medium**: Slows comprehension, weakens consistency, or mishandles a meaningful recoverable case.
- **Low**: Improves polish or local clarity without materially blocking work.

Use user impact, frequency, risk, confidence, and evidence—not visual conspicuousness or implementation ease.

## 5. Make every finding actionable

Use the following structure literally for every finding. Do not substitute an unlabeled paragraph, table row, or shorthand bullet.

```text
Priority: [Critical | High | Medium | Low] — Finding title
Evidence: What the artifact proves and where.
Impact: Which user, task, state, or risk is affected.
Recommendation: The smallest behavioral or structural correction.
Verification: The observable condition that confirms the correction.
```

Avoid “improve hierarchy,” “make cleaner,” “use a modal,” or “add polish” without explaining what changes, why, and how success is verified.

## 6. Separate preference from defect

Do not report a source recipe or personal taste as a defect. Exact radii, shadows, grids, type ratios, color shifts, chart treatments, bento layouts, motion styles, and admired-product patterns are contextual unless the product system or requirement establishes them.

Report a visual issue when it harms hierarchy, meaning, consistency, accessibility, state recognition, or task performance.

## 7. Report in improvement order

Return:

1. **Assessment** — task clarity, strongest evidence, and major risk
2. **Findings** — Critical through Low
3. **Missing states or evidence** — what cannot be evaluated
4. **Improvement sequence** — the fewest coherent passes, typically product model → flow/states → hierarchy/actions → responsiveness/accessibility → visual polish

Mention strengths only when they must be preserved during correction.

## Completion gate

Complete the Review workflow only when every material claim is grounded in supplied evidence, each finding includes evidence, impact, recommendation, verification, and priority, missing evidence is explicit, and the improvement sequence follows user impact.
