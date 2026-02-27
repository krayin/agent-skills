# krayin-crm/agent-skills

Agent skills for Krayin CRM — a Laravel-based CRM platform.

These skills provide domain-specific, reusable context for AI agents
working inside a Krayin CRM codebase.

## Available Skills

### `crm-package-development`

Package/module development in Krayin CRM.

Activates when: creating or modifying CRM packages, migrations, models,
repositories, routes, controllers, views, configs, menus, ACL, or system
configuration.

### `pest-testing`

Tests Krayin CRM using the Pest PHP framework.

Activates when: writing tests (unit or feature), adding assertions,
debugging test failures, working with datasets or mocking, or when the user
mentions test, spec, TDD, expects, assertion, coverage, or verifying behavior.

## Install

Install all skills from this repo into your AI agent:

```bash
npx skills add ./agent-skills
```

Install a specific skill only:

```bash
npx skills add ./agent-skills --skill "crm-package-development"
npx skills add ./agent-skills --skill "pest-testing"
```

Install for a specific agent:

```bash
npx skills add ./agent-skills -a claude-code
npx skills add ./agent-skills -a cursor
```

## Repository Structure

```text
agent-skills/
├── skills/
│   └── crm-package-development/
│       └── SKILL.md
│   └── pest-testing/
│       └── SKILL.md
└── AGENTS.md
```