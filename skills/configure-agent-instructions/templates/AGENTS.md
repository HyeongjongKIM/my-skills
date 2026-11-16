# Working on {{PROJECT_NAME}}

Read README.md and the selected task/specification when present before editing. If there is no task document, use the authorized request and its acceptance criteria as the task scope. Read architecture/tooling documents when present and relevant. Resolve all placeholders and remove unused document links when adopting this template.

## Workflow

Task tracking: {{TASK_QUEUE_PATH_OR_EXISTING_TRACKER_OR_NO_PLANNED_WORK}}

1. Inspect staged/unstaged Git changes and applicable nested instructions. Preserve unrelated work and completed task evidence.
2. Read the selected task or authorized request, scope and acceptance criteria. When phased tracking exists, select the earliest unfinished phase and earliest task whose dependencies are DONE; do not bypass blocked dependencies.
3. Apply the support rules below when the change requires external documentation. Implement only the selected scope; avoid unrelated redesigns, features and formatting.
4. Run {{APPLICABLE_VERIFICATION_COMMANDS}} for the affected behavior. Record actual commands/results and reasons for checks not run; distinguish existing failures from regressions. Build success alone does not prove runtime behavior.
5. Update existing task evidence/status and applicable phase/queue indexes; otherwise report results directly. Report changed files and purpose, verification, exclusions, blockers and the next action briefly; link existing evidence instead of repeating it.

## Support and dependency changes

Consult current official documentation when adding/upgrading dependencies, changing tool/framework configuration, introducing or changing external API use, or when support/behavior is uncertain. Check documentation for the installed or selected version; for dependency changes also check maintenance/security, engines and peers. Reuse findings while their versions and applicability remain valid. Routine prose or local application changes need no new research unless they raise one of these questions.

Use supported public APIs and documented configuration. Do not rely on private internals, arbitrarily patch dependencies, force incompatible installations or bypass engine/peer checks. Never weaken types, lint or tests, or add broad ignores, unsafe casts or suppressions solely to hide errors.

If support cannot be established, stop the dependent change, record the exact constraint and supported alternatives, and continue independent authorized work. Record decision-relevant official links and versions once in the task or tooling document. Keep documented support and actual local/runtime results distinct.

Select maintained, secure, compatible stable versions; no package version or major is mandated by this standard. Preserve existing constraints and avoid unrelated upgrades. Use local tools and retain the target lockfile for reproducibility.

## Documents

Use English for authored project documentation by default; preserve deliberate existing language conventions unless changing them is in scope.

Do not bulk-rename existing files or completed tasks. A scoped rename must update affected imports, links, globs, scripts and routes, then run applicable checks.

Keep guidance current without dated update notes. Preserve meaningful task evidence. Statuses are TODO, IN_PROGRESS, BLOCKED and DONE; DONE requires acceptance and applicable verification. Record blockers with impact and next action, and approved deferrals with the maintainer's decision.

## Project decisions

- Architecture/specification, when separate: {{ARCHITECTURE_AND_SPEC_PATHS_OR_NONE}}
- Runtime and package manager: {{NODE_VERSION_AND_PACKAGE_MANAGER_VERSION}}
- Commit policy: {{CONVENTIONAL_COMMITS_AND_SCOPE_POLICY}}
- Optional hooks/CI: {{HOOK_AND_CI_POLICY_OR_NONE}}
- Generated paths to avoid editing: {{GENERATED_PATHS}}
- Standard reference: {{SOURCE_SKILL_AND_REPOSITORY_FULL_SHA_OR_UNCOMMITTED_LOCAL_PATH}}

Do not commit secrets or overwrite existing tasks/specifications. Do not commit, create remotes, push, deploy or change external systems without authorization.
