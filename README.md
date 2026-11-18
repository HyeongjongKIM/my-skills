# my-skills

Personal development preferences packaged as independent, instruction-only skills. This repository contains English Markdown instructions, references and document templates. Configuration examples describe files to create or merge in an adopting project; they are not executable configuration for this repository.

## Choose a skill

| Skill | Use when | Result |
| --- | --- | --- |
| [configure-project-tooling](skills/configure-project-tooling/SKILL.md) | Set up or align TypeScript lint, format and type checking, with optional Astro/React, editor and hook integrations | Necessary configuration changes and actual verification in the target |
| [configure-agent-instructions](skills/configure-agent-instructions/SKILL.md) | Introduce or refine persistent AI-agent instructions and project document navigation | Customized AGENTS.md and only the supporting documents needed |
| [plan-implementation](skills/plan-implementation/SKILL.md) | Turn requirements into bounded phases and tasks | Dependencies, acceptance criteria, verification plans and consistent task indexes |

Select only the skills needed for the current request. Installing every skill in a target project is optional. Each has its own completion conditions and bundles its required references/templates; none requires a sibling skill to be installed. Preserve the target's instructions, conventions, user changes and completed evidence. Persistent working rules belong in the target AGENTS.md rather than depending on a skill being invoked for every implementation task.

## Structure

```text
AGENTS.md
README.md
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

This repository is a collection of independently usable skills. Each directory directly under `skills/` contains its own SKILL.md, references and templates. Use selected complete skill folders; the repository root is a catalog, not an installable skill.

After publishing this repository, ask the Codex skill installer to install the desired folder from its Git repository URL and path. Specify `skills/configure-project-tooling`, `skills/configure-agent-instructions` or `skills/plan-implementation`. Use the actual remote URL and an existing revision; no remote URL or committed revision is assumed here. Follow the current [official installation documentation](https://learn.chatgpt.com/docs/build-skills) for the installed host.

For local use without publishing, copy the desired complete skill folders into the adopting project's `.agents/skills/` directory. Keep references and templates with each SKILL.md. Cloning this source repository elsewhere alone does not register the skills. Installation scope is a user or target-project decision; this repository does not automatically register skills or change other projects.

Once installed, invoke the selected skill from the target project:

- “Use $configure-project-tooling to align this project's lint, format and type checks. Preserve existing conventions and report exclusions.”
- “Use $configure-agent-instructions to tailor AGENTS.md and document navigation to this repository.”
- “Use $plan-implementation to turn these requirements into phased tasks without implementing them.”

In Codex CLI or the IDE extension, use `/skills` to inspect available skills. If discovery has not refreshed, restart Codex. See the [Agent Skills specification](https://agentskills.io/specification) for the instruction format. This repository remains Markdown-only; it contains no executable installer or plugin manifest.

## When to keep a skill installed

`configure-project-tooling` is used for initial setup and deliberate tooling changes, such as updating lint rules or framework integrations. It is not required for routine implementation after setup. Keep it in this source collection for reuse across projects; the configured target runs with its own dependencies, scripts and configuration files.

After configuration and applicable target verification are complete, you may remove a project-local copy or registration of this skill. Preserve the resulting configuration, dependencies, lockfile, commands, project decisions and verification evidence. Removing skill instructions does not uninstall the development tools. Keep or reinstall the skill when another tooling change is needed; do not remove it automatically as part of setup.

`configure-agent-instructions` produces persistent target instructions and navigation. The resulting AGENTS.md and documents remain useful after that skill is removed. `plan-implementation` is reusable whenever new requirements need task plans; existing plans and evidence remain in the target independently of the skill.

For Tailwind projects, `configure-agent-instructions` records the inline utility authoring preference in the target AGENTS.md. `configure-project-tooling` configures canonical-class linting separately. Either skill can be used independently; routine authoring follows the target instructions and installed tooling after setup skills are removed.

Keep ongoing project rules and verification commands in the target's existing AGENTS.md, README or tooling document as appropriate. They must not require an installed setup skill or link to its project-local installation path. Installing a skill, applying its instructions and retaining its outputs are separate choices.

## Stable preferences and target decisions

Tooling preferences include Flat Config, selected TypeScript checks, kebab-case source filename linting, separate Prettier formatting, local editor tools and optional hook/commit-check automation. Tailwind projects prefer inline utility classes and canonical-class linting where supported. Workflow preferences include bounded work, Conventional Commits and concise verification evidence. Concrete task planning is separate from adopting instructions.

No tool version or major release is mandated. Preserve the [version and support policy](skills/configure-project-tooling/references/adoption.md#version-and-support-policy): select maintained, secure, compatible stable combinations at adoption, preserve existing constraints and avoid unrelated upgrades. Deployment, branches, workspace names, package managers and commit scopes remain target decisions.

Record the selected skill name and the source repository's full SHA (plus tag if used) in the target README or relevant decision document. Resolve tags to full SHAs. For an uncommitted local source, record its path and that limitation rather than inventing a revision. A source reference is not a package-version requirement or an automatic update mechanism.

## Maintaining this repository

Read [AGENTS.md](AGENTS.md). No dependencies are installed and no formatting, lint, typecheck, tests, builds, hooks or document verification scripts are run here. Review Markdown through file reads and searches; executable configuration and verification belong to the adopting project. Do not commit, create remotes, push or deploy without authorization.
