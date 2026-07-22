# Artilishes Skills

A curated collection of skills for AI coding agents.

## Available skills

### [Apply Engineering Principles](skills/apply-engineering-principles/)

Apply maintainability, architecture, security, data ownership, reliability, operability, and client-handover principles to consequential engineering work.

Use this skill to:

- Make or review architecture, platform, dependency, and integration decisions
- Plan or implement sizeable changes, refactors, and migrations
- Review code and system design using evidence, risk, and long-term ownership
- Give foundational areas such as authentication, authorization, payments, multi-tenancy, and data modeling appropriate rigor

The skill calibrates its process to impact, reversibility, uncertainty, and operational span. It does not apply to trivial edits, mechanical formatting, or narrowly prescribed changes that require no engineering judgment.

### [SaaS Product Design](skills/saas-product-design/)

Design, implement, refactor, and review SaaS product interfaces, including dashboards, CRUD and admin tools, data-heavy workflows, navigation, forms, settings, builders, onboarding, AI interfaces, and responsive states.

Use this skill to:

- Design product flows and implementation-ready interface specifications
- Implement or refactor interfaces within an existing codebase
- Review screenshots, design files, code, or running interfaces
- Improve hierarchy, data representation, progressive disclosure, feedback, recovery, accessibility, responsive behavior, and visual language

The skill focuses on software-product interfaces. It does not cover marketing sites, landing pages, portfolios, or brand identity.

## Installation

Install one or both skills with the Skills CLI:

```bash
npx skills add artilishes/skills --skill apply-engineering-principles
npx skills add artilishes/skills --skill saas-product-design
```

To install a skill globally for a specific agent:

```bash
npx skills add artilishes/skills --skill apply-engineering-principles --agent codex --global
npx skills add artilishes/skills --skill saas-product-design --agent codex --global
```

## Usage

Invoke the skill explicitly or let a compatible agent select it automatically:

```text
Use $apply-engineering-principles to review this authentication migration and recommend a safe incremental approach.
```

```text
Use $saas-product-design to design the states and responsive behavior for this billing workflow.
```

```text
Use $saas-product-design to implement this dashboard in the existing codebase.
```

```text
Use $saas-product-design to review this settings screen and prioritize evidence-backed improvements.
```

Provide the relevant requirements, artifacts, design links, code, or repository context with the request.

## Project-level AGENTS.md guidance

To make the engineering skill available for consequential work without loading it for every small edit, add this instruction to a project's `AGENTS.md`:

```markdown
Use `$apply-engineering-principles` for architecture decisions, technical plans,
sizeable implementations or refactors, engineering reviews, migrations,
integrations, and changes to foundational or difficult-to-reverse systems.
Do not invoke it for trivial or mechanical edits.
```

Keep stack choices, repository boundaries, exact verification commands, local conventions, and project architecture in the project's own instructions.

## Attribution

The SaaS Product Design skill draws inspiration from the product design lessons shared by [Kole Jain](https://www.kolejain.com/), including the videos on [his YouTube channel](https://www.youtube.com/@KoleJain). I am a great fan of Kole's work and grateful to him for making his knowledge and perspective available to the design community.

## License

This repository is available under the [MIT License](LICENSE).
