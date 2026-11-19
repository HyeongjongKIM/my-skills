# Working on {{PROJECT_NAME}}

Read README.md and the selected task/specification when present before editing. If there is no task document, use the authorized request and its acceptance criteria as the task scope. Read architecture/tooling documents when present and relevant. Resolve all placeholders and remove unused document links when adopting this template.

## Workflow

Task tracking: {{TASK_QUEUE_PATH_OR_EXISTING_TRACKER_OR_NO_PLANNED_WORK}}

1. Inspect staged/unstaged Git changes and applicable nested instructions. Preserve unrelated work and completed task evidence.
2. Read the selected task or authorized request, scope and acceptance criteria. When phased tracking exists, select the earliest unfinished phase and earliest task whose dependencies are DONE; do not bypass blocked task or phase prerequisites. If that phase has no eligible work, continue independent authorized work in another phase only with all its prerequisites satisfied.
3. Apply the support rules below when the change requires external documentation. Implement only the selected scope; avoid unrelated redesigns, features and formatting.
4. Run {{APPLICABLE_VERIFICATION_COMMANDS}} for the affected behavior. Record actual commands/results and reasons for checks not run; distinguish existing failures from regressions. Build success alone does not prove runtime behavior.
5. Update existing task evidence/status and applicable phase/queue indexes; otherwise report results directly. Report changed files and purpose, verification, exclusions, blockers and the next action briefly; link existing evidence instead of repeating it.

## Planning and completion gates

Use one agent sequentially; a selected playbook supplies the sequence and skills supply bounded methods. For small work, use a brief checklist instead of creating phases or another tracker.

Before implementation, compare requirements with tasks/checklist: functional and relevant nonfunctional coverage, architecture/data flow, API/UI/state/failure paths, feasibility, risks, dependencies/cycles/order, duplicate/conflicting scope and observable acceptance. Record this Planning Quality Gate in existing tracking or report directly. Report contradictions by location, cause, impact and resolution; block affected tasks while continuing independent authorized work.

Never change a task ID that has ever left TODO, including one later returned to TODO. Preserve IDs when history is unknown. Add collision-free IDs without renumbering; retain status transitions/reasons, split/merge/supersession records, references and evidence. Superseded work does not automatically satisfy dependencies or become DONE. Add new linked tasks for additional scope after DONE; change an inaccurate status only with evidence, preserving its history.

When omissions, constraints, design changes or failed checks appear, compare the cause/impact against specifications/tasks, decide corrective or new work, update coverage/dependencies/acceptance with history intact and recheck affected planning assumptions. Obtain user decisions for material requirement/architecture changes outside authorization; handle safe refinements within scope.

For repeated mistakes, consider recurrence, impact and upkeep. Prefer architecture/API prevention, static checks, behavioral tests, runtime checks, then prose for remaining judgment. Reuse existing safeguards and verify selected automation against valid and invalid cases in the target; do not add a rule for every mistake or leave automatable recurring rules only in prose.

Before claiming completion, perform a separate Completion Gate against original requirements and approved changes, actual behavior, acceptance, mandatory verification, missed scope and unresolved material issues. DONE tasks alone are insufficient. Report COMPLETED only with requirements and mandatory checks satisfied; PARTIAL for incomplete implementation/verification; BLOCKED when a material issue prevents progress. Name the agreed scope, explicit deferrals, unexecuted/failed checks, risks and next actions. Never present unrun checks as passed or a plan as implemented.

## Context and resume

Read only relevant documents and selected playbook/skill references. Reuse findings until changed code, versions or assumptions require rechecking affected areas and integration boundaries. Preserve required verification regardless of token cost.

For long work, keep current phase/task, next eligible action, decision/blocker links, incomplete changes and verification links in one checkpoint within existing tracking. Keep detailed evidence in tasks. On resume, read that checkpoint and applicable instructions/relevant tasks, inspect Git changes and reconcile stale evidence before continuing. Do not create duplicate status files or reset completed records.

## Support and dependency changes

Consult current official documentation when adding/upgrading dependencies, changing tool/framework configuration, introducing or changing external API use, or when support/behavior is uncertain. Check documentation for the installed or selected version; for dependency changes also check maintenance/security, engines and peers. Reuse findings while their versions and applicability remain valid. Routine prose or local application changes need no new research unless they raise one of these questions.

Use supported public APIs and documented configuration. Do not rely on private internals, arbitrarily patch dependencies, force incompatible installations or bypass engine/peer checks. Never weaken types, lint or tests, or add broad ignores, unsafe casts or suppressions solely to hide errors.

If support cannot be established, stop the dependent change, record the exact constraint and supported alternatives, and continue independent authorized work. Record decision-relevant official links and versions once in the task or tooling document. Keep documented support and actual local/runtime results distinct.

Select maintained, secure, compatible stable versions; no package version or major is mandated by this standard. Preserve existing constraints and avoid unrelated upgrades. Use local tools and retain the target lockfile for reproducibility.

## Documents

Use English for authored project documentation by default; preserve deliberate existing language conventions unless changing them is in scope.

Do not bulk-rename existing files or completed tasks. A scoped rename must update affected imports, links, globs, scripts and routes, then run applicable checks.

Keep guidance current without dated update notes. Preserve meaningful task evidence. Statuses are TODO, IN_PROGRESS, BLOCKED and DONE; DONE requires acceptance and applicable verification. Record blockers with impact and next action, and approved deferrals with the maintainer's decision.

## Styling

Keep this section only when the target uses Tailwind CSS; merge it with existing styling instructions and preserve deliberate project decisions.

Prefer Tailwind utility classes directly in markup `class` or JSX `className`. Do not extract CSS classes or `@apply` solely to shorten an attribute. Use shared components, conditional class helpers and custom CSS when needed. Keep conditional alternatives as complete utility strings rather than constructing class-name fragments. Attributes may span multiple lines; this preference does not mean using inline `style` attributes.

## Project decisions

- Architecture/specification, when separate: {{ARCHITECTURE_AND_SPEC_PATHS_OR_NONE}}
- Runtime and package manager: {{NODE_VERSION_AND_PACKAGE_MANAGER_VERSION}}
- Commit policy: {{CONVENTIONAL_COMMITS_AND_SCOPE_POLICY}}
- Optional hooks/CI: {{HOOK_AND_CI_POLICY_OR_NONE}}
- Generated paths to avoid editing: {{GENERATED_PATHS}}
- Standard reference: {{SOURCE_SKILL_AND_REPOSITORY_FULL_SHA_OR_UNCOMMITTED_LOCAL_PATH}}

Do not commit secrets or overwrite existing tasks/specifications. Do not commit, create remotes, push, deploy or change external systems without authorization.
