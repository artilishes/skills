# Artilishes Skills

A curated collection of skills for AI coding agents.

## Available skills

### [SaaS Product Design](.agents/skills/saas-product-design/)

Design, implement, refactor, and review SaaS product interfaces, including dashboards, CRUD and admin tools, data-heavy workflows, navigation, forms, settings, builders, onboarding, AI interfaces, and responsive states.

Use this skill to:

- Design product flows and implementation-ready interface specifications
- Implement or refactor interfaces within an existing codebase
- Review screenshots, design files, code, or running interfaces
- Improve hierarchy, data representation, progressive disclosure, feedback, recovery, accessibility, responsive behavior, and visual language

The skill focuses on software-product interfaces. It does not cover marketing sites, landing pages, portfolios, or brand identity.

## Installation

Install with the Skills CLI:

```bash
npx skills add artilishes/skills --skill saas-product-design
```

To install it globally for a specific agent:

```bash
npx skills add artilishes/skills --skill saas-product-design --agent codex --global
```

## Usage

Invoke the skill explicitly or let a compatible agent select it automatically:

```text
Use $saas-product-design to design the states and responsive behavior for this billing workflow.
```

```text
Use $saas-product-design to implement this dashboard in the existing codebase.
```

```text
Use $saas-product-design to review this settings screen and prioritize evidence-backed improvements.
```

Provide the relevant requirements, screenshots, design links, code, or repository context with the request.

## License

This repository is available under the [MIT License](LICENSE).
