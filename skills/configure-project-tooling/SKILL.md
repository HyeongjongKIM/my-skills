---
name: configure-project-tooling
description: Configure or align TypeScript linting, formatting and type checking in an existing or new project, with optional Astro, React, VS Code and Git hook integrations. Use for initial setup or deliberate tooling changes; not for routine implementation, installing an agent workflow or planning feature work.
---

# Configure project tooling

Apply selected tooling preferences in the target project. Read the [version and support policy](references/adoption.md) and use the relevant sections of the [tooling examples](references/tooling.md) and [official sources](references/official-sources.md). Read [Astro](references/astro.md), [React](references/react.md) and [Tailwind](references/tailwind.md) only for integrations present or explicitly selected for the target. For Astro with React, read both framework sections.

## Procedure

1. Read applicable target instructions and relevant project documents. Inspect staged and unstaged changes if the target uses Git. Inventory the runtime, package manager, manifests, lockfile, TypeScript projects and existing tooling for the requested scope. For a new project, confirm the intended runtime, package manager and framework from the request or project decisions before installing. Apply Git hooks only in a target Git repository. Preserve unrelated work and existing constraints.
2. Select a bounded set of changes. Default preferences are Flat Config, TypeScript recommended rules plus selected typed checks, kebab-case source filename linting, separate Prettier with singleQuote=true and trailingComma=all, and local editor tools when used. Preserve deliberate existing style unless changing it is in scope. Hooks and automated commit checks are optional; select each explicitly.
3. Check current official documentation, maintenance/security information, engines and peers for selected dependencies and integrations. Use supported public APIs. Follow the bundled version policy; never force incompatible installs, patch vendors arbitrarily or weaken checks to hide errors. If support cannot be established, stop dependent changes, report exact constraints and supported alternatives, and continue independent authorized work.
4. Merge only necessary settings into existing files. Preserve arrays, scripts, lifecycle commands and workspace boundaries. Avoid copying a reference application's structure or making broad renames/reformatting. Configuration snippets are examples, not files to copy wholesale. Resolve paths, commands and placeholders. Do not introduce project instructions or a task queue as a side effect.
5. Install only selected dependencies in the actual target and run applicable checks there. Verify configuration loading, intended lint diagnostics, typed coverage, formatting and real behavior affected by changes. Verify editor behavior and actual hook dispatch only for selected integrations. Preserve partially staged work; keep local-hook and CI evidence distinct.
6. Document ongoing settings, commands, exclusions and support decisions in their existing README or tooling sections. Record task-specific verification in the existing task evidence or report it directly when there is no task record. Use the optional [tooling template](templates/docs/tooling.md) only when needed.

## Completion

Report changed files and purposes, exact checks and observed results, checks not run and reasons, exclusions, blockers and next actions. An empty test suite is not behavioral coverage and a successful build alone does not establish runtime behavior. Record the source skill/repository reference, using a full SHA or identifying an uncommitted local path. Leave package manager, deployment, branches, workspace names and commit scopes to the target. Do not commit, create remotes, push or deploy without authorization.

The configured target must work independently of this skill remaining installed. Keep actual commands and ongoing tooling decisions in the existing target README, tooling document or applicable AGENTS.md, without links to a project-local skill installation. This does not require introducing new project instructions. Explain that the user may remove a project-local copy or registration after setup and applicable verification, while preserving configurations, dependencies, lockfile and evidence. Do not remove the skill automatically. It can be reused for later tooling changes.

This skill contains instructions and Markdown examples only. When maintaining its source repository, follow that repository's documentation-only restrictions; do not install or execute target checks there.
