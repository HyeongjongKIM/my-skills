# my-skills

Personal development preferences packaged as independent, instruction-only skills. This repository contains English Markdown instructions, references and document templates. Configuration examples describe files to create or merge in an adopting project; they are not executable configuration for this repository.

## Choose a skill

| Skill | Use when | Result |
| --- | --- | --- |
| [configure-project-tooling](skills/configure-project-tooling/SKILL.md) | Set up or align TypeScript lint, format and type checking, with optional Astro/React, editor and hook integrations | Necessary configuration changes and actual verification in the target |
| [configure-agent-instructions](skills/configure-agent-instructions/SKILL.md) | Introduce or refine persistent AI-agent instructions, including model routing and delegation | Concise rules in the target's active project instructions, procedure navigation and optional host-specific settings |
| [plan-implementation](skills/plan-implementation/SKILL.md) | Turn requirements into bounded phases and tasks | Proportionate plans, stable task identity/history, dependency review and Planning Quality Gate |

Select only the skills needed for the current request. Each bundles its required references and templates. Core rules and mandatory procedure pointers belong in the target's active project instructions. Detailed task lifecycle, gates and resume belong in existing execution or tracking documents, available without invoking a skill.

## Structure

```text
AGENTS.md
README.md
playbooks/
  README.md
  gates.md
  project-development.md
  feature-development.md
  bug-fix.md
  refactoring.md
docs/
  harness/codex.md
  harness/claude-code.md
  workflow-scenarios.md
skills/
  configure-project-tooling/
    SKILL.md
    references/
      adoption.md
      tooling.md
      official-sources.md
      astro.md
      react.md
      tailwind.md
    templates/docs/tooling.md
  configure-agent-instructions/
    SKILL.md
    references/
      workflow.md
      documents.md
      model-routing.md
    templates/
      AGENTS.md
      README.md
      docs/architecture.md
  plan-implementation/
    SKILL.md
    references/planning.md
    templates/tasks/
      README.md
      01-phase/
        README.md
        01-task.md
```

## Use from another project

This repository is a collection of independently usable skills. Each directory directly under `skills/` contains its own SKILL.md, references and templates. Install selected complete skill folders from the catalog. The [agent efficiency policy](skills/configure-agent-instructions/references/workflow.md#agent-efficiency-and-model-routing) covers model choice, delegation and context use. Its [model routing reference](skills/configure-agent-instructions/references/model-routing.md) provides optional target configuration examples.

For local use, follow the discovery instructions for [Codex](docs/harness/codex.md) or [Claude Code](docs/harness/claude-code.md). Copy the selected complete skill folders, including references and templates, to the host's project skill directory. Cloning the source repository alone does not register its skills. Preserve any existing same-name installation until its source and intended scope are confirmed.

When the desired revision is accessible on GitHub, Codex can also use `$skill-installer`. Provide the real repository URL, revision and selected `skills/<skill-name>` path. Check the destination scope before installing. [Codex skills documentation](https://learn.chatgpt.com/docs/build-skills#install-curated-skills-for-local-use), [official installer instructions](https://github.com/openai/skills/blob/main/skills/.system/skill-installer/SKILL.md).

Once installed, invoke the selected skill from the target project. These examples use Codex's `$` syntax. Claude Code uses `/<skill-name>`.

- “Use $configure-project-tooling to align this project's lint, format and type checks. Preserve existing conventions and report exclusions.”
- “Use $configure-agent-instructions to tailor AGENTS.md and document navigation to this repository.”
- “Use $plan-implementation to turn these requirements into phased tasks without implementing them.”

In Codex CLI or the IDE extension, use `/skills` to inspect available skills. If discovery has not refreshed, restart Codex. See the [Agent Skills specification](https://agentskills.io/specification) for the instruction format. This repository remains Markdown-only; it contains no executable installer or plugin manifest.

## Execute a playbook

Codex is the default host; see [Codex](docs/harness/codex.md) and [Claude Code](docs/harness/claude-code.md) for actual discovery/invocation differences. A skill supplies a bounded method; a playbook orders execution and gates; one agent runs it sequentially. Existing skills work without playbooks, and playbooks can use target instructions when optional skills are absent. Planning-only skill invocation never authorizes implementation by itself.

Choose [project-development](playbooks/project-development.md), [feature-development](playbooks/feature-development.md), [bug-fix](playbooks/bug-fix.md) or [refactoring](playbooks/refactoring.md). Read only the selected procedure and its [gate criteria](playbooks/gates.md), then relevant skill references as needed. For another project, copy the complete `playbooks/` directory to a chosen location such as `docs/playbooks/`, or provide an accessible source path. This is Markdown navigation, not automatic registration; keep relative links intact. See [playbook adoption](playbooks/README.md).

Example Codex requests below assume the target chose `docs/playbooks/` and installed any named skill:

- New project: “Read docs/playbooks/project-development.md. Analyze these requirements, use $plan-implementation to plan them, review the Planning Quality Gate, then implement and verify the authorized scope.”
- Feature: “Follow docs/playbooks/feature-development.md to add this feature. Preserve existing contracts and include relevant regression evidence.”
- Bug: “Follow docs/playbooks/bug-fix.md for this reproduction. Keep the procedure proportionate and verify the correction.”
- Resume: “Resume using the existing task queue checkpoint and docs/playbooks/project-development.md. Inspect Git changes, preserve task IDs/history, reconcile stale evidence and continue the next eligible task.”
- Revalidate a completed project: “Apply the Completion Gate in docs/playbooks/gates.md against the original requirements and approved changes, even if every task is DONE. Report missing behavior, failed/unrun checks and new work without resetting completed records.”

Requirements map to bounded tasks or a small checklist, with observable acceptance and verification. Planning review checks coverage and consistency; completion review compares actual behavior/evidence with original requirements. Report COMPLETED, PARTIAL or BLOCKED; DONE tasks alone do not establish completion. Existing execution/tracking documents own lifecycle and continuity; every task ID is immutable from creation and never reused, including cancelled tasks. Required verification is never omitted to save tokens.

The [scenario review](docs/workflow-scenarios.md) records normal, failure, interruption and resume walkthroughs. It is document review, not a claim of executed agent or application tests.

The design selectively draws on [pstack](https://github.com/cursor/plugins/tree/main/pstack) for verifiable work units and structural learning, and the [BigGo discussion summary](https://finance.biggo.com/podcast/5a6129233f489c0e) for investing in architecture and verification before prose. The sequential playbooks apply those ideas to Markdown procedures and gates. External pages are optional background reading.

## When to keep a skill installed

`configure-project-tooling` is used for initial setup and deliberate tooling changes, such as updating lint rules or framework integrations. It is not required for routine implementation after setup. Keep it in this source collection for reuse across projects; the configured target runs with its own dependencies, scripts and configuration files.

After configuration and applicable target verification are complete, you may remove a project-local copy or registration of this skill. Preserve the resulting configuration, dependencies, lockfile, commands, project decisions and verification evidence. Removing skill instructions does not uninstall the development tools. Keep or reinstall the skill when another tooling change is needed; do not remove it automatically as part of setup.

`configure-agent-instructions` produces core target instructions and navigation, preserving detailed safeguards in their existing procedure owners. The resulting instructions, documents and any selected agent settings remain usable after that skill is removed. `plan-implementation` is reusable whenever new requirements need task plans; existing plans and evidence remain in the target independently of the skill.

For Tailwind projects, `configure-agent-instructions` records the inline utility authoring preference in the target's active instructions. `configure-project-tooling` configures canonical-class linting separately. Either skill can be used independently; routine authoring follows the target instructions and installed tooling after setup skills are removed.

Keep ongoing project rules and verification commands in the target's existing project instructions, README or tooling document as appropriate. They must not require an installed setup skill or link to its project-local installation path. Installing a skill, applying its instructions and retaining its outputs are separate choices.

## Stable preferences and target decisions

Tooling preferences include Flat Config, selected TypeScript checks, kebab-case source filename linting, separate Prettier formatting, local editor tools and optional hook/commit-check automation. Tailwind projects prefer inline utility classes and canonical-class linting where supported. Workflow preferences include bounded work, Conventional Commits and concise verification evidence. Concrete task planning is separate from adopting instructions.

No tool version or major release is mandated. Preserve the [version and support policy](skills/configure-project-tooling/references/adoption.md#version-and-support-policy): select maintained, secure, compatible stable combinations at adoption, preserve existing constraints and avoid unrelated upgrades. Deployment, branches, workspace names, package managers and commit scopes remain target decisions.

Record the selected skill name and the source repository's full SHA (plus tag if used) in the target README or relevant decision document. Resolve tags to full SHAs. For an uncommitted local source, record its path and that limitation rather than inventing a revision. A source reference is not a package-version requirement or an automatic update mechanism.

## Maintaining this repository

Read [AGENTS.md](AGENTS.md). No dependencies are installed and no formatting, lint, typecheck, tests, builds, hooks or document verification scripts are run here. Review Markdown through file reads and searches; executable configuration and verification belong to the adopting project. Do not commit, create remotes, push or deploy without authorization.
