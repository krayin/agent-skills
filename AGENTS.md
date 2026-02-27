# Krayin CRM Guidelines

Krayin CRM is a Laravel-based CRM platform with a modular package
architecture under `packages/Webkul/`. These guidelines are tailored to
developing and extending Krayin CRM in a safe, upgrade-friendly way.

## Foundational Context

This application is **Krayin CRM** built on Laravel. You must be
comfortable with Laravel conventions and Krayin’s package-based
architecture.

### Technology Stack

- **PHP**: 8.2 (see `composer.json`)
- **Laravel**: v10
- **Laravel Sanctum**: v3
- **Konekt Concord**: v1 (package/module management)
- **Prettus L5 Repository**: v2 (repository pattern)
- **Pest**: v2 (testing)
- **PHPUnit**: v10 (testing)
- **Laravel Pint**: v1 (formatting)

### Krayin Core Packages

Krayin uses a modular package structure in `packages/Webkul/`.
Common packages include:

- **Admin**
- **Core**
- **Lead**
- **Contact**
- **Email**
- **Marketing**
- **Quote**
- **Product**
- **User**
- **Warehouse**
- **Automation**

## Skills Activation

This project has domain-specific skills available. You MUST activate the
relevant skill whenever you work in that domain.

- `crm-package-development` — Package/module development in Krayin CRM.
  Activate when creating or modifying CRM packages, migrations, models,
  repositories, routes, controllers, views, configs, menus, ACL, or system
  configuration.
- `pest-testing` — Testing in Krayin CRM using Pest.
  Activate when writing tests (unit or feature), adding assertions,
  debugging test failures, working with datasets or mocking, or when the user
  mentions test, spec, TDD, expects, assertion, coverage, or verifying behavior.

## Krayin Architecture

### Package Structure

Every Krayin package follows a standardized structure:

```text
packages/
└── Webkul/
    └── PackageName/
        ├── src/
        │   ├── Providers/
        │   │   └── PackageServiceProvider.php
        │   ├── Models/
        │   ├── Contracts/
        │   ├── Repositories/
        │   ├── Http/
        │   │   ├── Controllers/
        │   │   └── Requests/
        │   ├── Routes/
        │   │   ├── admin.php
        │   │   └── api.php
        │   ├── Database/
        │   │   └── Migrations/
        │   ├── Resources/
        │   │   └── views/
        │   └── Config/
        │       ├── package.php
        │       ├── menu.php
        │       ├── core_config.php
        │       └── acl.php
        └── composer.json
```

### Repository Pattern

Krayin uses the Prettus L5 Repository pattern. Prefer repositories for
data access and avoid raw queries where a repository exists.

### Service Providers

Service providers should:

- Load routes, migrations, translations, and views from the package
- Merge package configuration using `$this->mergeConfigFrom()`
- Register models via Concord where required

## Conventions

- Follow existing code conventions in this application.
- Use descriptive names for variables and methods.
- Use PHPDoc blocks for classes and methods.
- Do not modify core Krayin files unless explicitly required.
- Use migrations for all database changes.

## Frontend Bundling

If UI changes aren’t reflected, you may need `npm run dev` or
`npm run build` (see `vite.config.js`).

## Replies

- Be concise and focus on what matters.