# Artilishes Skills

[![skills.sh](https://skills.sh/b/artilishes/skills)](https://skills.sh/artilishes/skills)

A curated collection of Agent Skills for Codex and other compatible AI agents. Each skill packages focused instructions and supporting references so an agent can perform a specialized workflow consistently without turning every request into a large prompt.

The collection follows the [Agent Skills specification](https://agentskills.io/specification). Source skills live under [`.agents/skills/`](.agents/skills/), a repository layout discovered by the Skills CLI and compatible agents; optional package artifacts live under [`dist/`](dist/).

## Available skills

| Skill | Purpose | Source | Package |
| --- | --- | --- | --- |
| SaaS Product Design | Design, implement, refactor, and review product interfaces for dashboards, CRUD and admin tools, forms, settings, builders, onboarding, AI features, data-heavy workflows, and responsive states. | [`.agents/skills/saas-product-design`](.agents/skills/saas-product-design/) | [`dist/saas-product-design.skill`](dist/saas-product-design.skill) |

### SaaS Product Design

Use this skill when an agent needs to reason about product behavior as well as interface presentation. It provides separate workflows for:

- Designing product flows and implementation-ready interface specifications
- Implementing or refactoring an interface within an existing codebase
- Reviewing screenshots, design files, code, or running interfaces with evidence-backed findings
- Handling hierarchy, data representation, progressive disclosure, feedback, recovery, accessibility, responsive behavior, and visual language

The skill is intended for software-product interfaces. It does not cover marketing sites, landing pages, portfolios, brand identity, or framework-specific visual recipes.

## Installation

Inspect the skills available in this repository:

```bash
npx skills add artilishes/skills --list
```

Install the SaaS Product Design skill:

```bash
npx skills add artilishes/skills --skill saas-product-design
```

Target Codex explicitly, or add `--global` to make the installation available across projects:

```bash
npx skills add artilishes/skills --skill saas-product-design --agent codex
npx skills add artilishes/skills --skill saas-product-design --agent codex --global
```

The Skills CLI selects the correct installation path for the requested agent. Clients that support `.skill` packages can instead use the artifact under [`dist/`](dist/).

## Usage

Agents can select a skill automatically from its description, or you can invoke it explicitly:

```text
Use $saas-product-design to design the states and responsive behavior for this billing workflow.
```

```text
Use $saas-product-design to implement this dashboard in the existing codebase.
```

```text
Use $saas-product-design to review this settings screen and prioritize evidence-backed improvements.
```

Provide the relevant requirements, screenshots, design links, code, or repository context with the request. The skill distinguishes supplied facts from assumptions and proposals rather than inventing missing product rules.

## Repository structure

```text
.
├── .agents/
│   └── skills/
│       └── saas-product-design/
│           ├── SKILL.md              # Trigger metadata and core workflow
│           ├── agents/openai.yaml    # Codex-facing display metadata
│           └── references/           # Context loaded for specific workflows
└── dist/
    └── saas-product-design.skill # Generated installable package
```

`.agents/skills/` is the source of truth. Files under `dist/` are generated artifacts and should be rebuilt after source changes.

## Development

When changing an existing skill:

1. Edit the source under `.agents/skills/<skill-name>/`.
2. Keep `SKILL.md` concise and move conditional detail into directly linked reference files.
3. Keep private research, source matrices, credentials, and internal provenance outside the repository and package.
4. Validate frontmatter, links, and package contents.
5. Confirm that the Skills CLI discovers the collection with `npx skills add . --list`.
6. Forward-test meaningful workflow changes on realistic tasks before publishing them.
7. Rebuild the `.skill` artifact and verify that its extracted contents match the source directory.

To rebuild the current package:

```bash
cd .agents/skills
zip -0 -r -X /tmp/saas-product-design.skill saas-product-design
mv /tmp/saas-product-design.skill ../../dist/saas-product-design.skill
```

Inspect the resulting archive before publishing:

```bash
unzip -l dist/saas-product-design.skill
```

## Adding a skill

Create a self-contained folder under `.agents/skills/` with:

- A required `SKILL.md` containing `name` and `description` frontmatter
- Clear trigger language describing what the skill does and when it applies
- Only the scripts, references, or assets needed at runtime
- Agent-facing metadata where supported
- A validated package under `dist/` when the skill is ready for distribution

Add the skill to the catalog in this README and include concise usage examples. Avoid process diaries, copied source material, and private evidence records in distributable skill folders.

## References

- [Agent Skills specification](https://agentskills.io/specification)
- [Using skills in Codex](https://developers.openai.com/codex/skills)
- [Anthropic Skills repository](https://github.com/anthropics/skills)
- [Vercel Agent Skills repository](https://github.com/vercel-labs/agent-skills)

## License

This repository is available under the [MIT License](LICENSE).
