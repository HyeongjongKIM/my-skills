# Working contract for an AI agent

The user's current request and the target's applicable instructions govern adoption. These preferences are a guide to deliberate integration, not permission to replace a project wholesale.

This guide owns the persistent working rules for the agent-instructions skill. The target [AGENTS template](../templates/AGENTS.md) carries them into an adopting project. Tool configuration and concrete task planning are separate requests.

## Requirement levels

**Required** means a working safeguard or a condition needed for a selected setting to function. **Default preference** means apply when suitable and explain a conflict or exclusion. **Optional** means select only when the target uses the relevant technology or needs the document scale.

| Level | Preference | Purpose / condition |
| --- | --- | --- |
| Required | Preserve user work and use supported public APIs | All work |
| Default preference | English documents | Preserve deliberate existing language conventions unless changing them is in scope |
| Default preference | Conventional Commits | Scope vocabulary remains a target decision |
| Default preference | Inline Tailwind utility classes | Only when the target uses Tailwind CSS; preserve deliberate existing styling decisions |
| Default preference | Phased task queue with phase/task indexes | When concrete work is planned; preserve existing tracking and do not create empty phases |

## Before editing the target

Read applicable AGENTS.md, README, Git status including staged/unstaged changes, relevant specifications, existing configurations, dependencies and task evidence. Identify already completed work. Select a bounded task with satisfied dependencies; preserve unrelated code, settings, dependencies and documents.

Consult current official documentation when adding/upgrading dependencies, changing tool/framework configuration, introducing or changing external API use, or when support/behavior is uncertain. Use the installed or selected version’s documentation; check maintenance/security, engines and peers for dependency changes. Reuse findings while their versions and applicability remain valid. Routine prose and local application changes need no new research unless they raise these questions. For new dependencies, select maintained, secure, compatible stable versions; no version or major is mandated. Preserve existing constraints and avoid unrelated upgrades. Record selected versions and retain the target lockfile. Historical examples are evidence, never installation defaults.

## During work

Make small changes within the selected scope. Use documented supported configurations. Do not depend on private APIs or undocumented internals, patch vendors arbitrarily, force incompatible installs or introduce workaround architectures to evade support constraints. Never weaken types, lint or tests, add broad ignores, unsafe casts or suppressions solely to conceal errors.

If support cannot be established, stop the dependent work and report the exact constraint, official sources and supported alternatives. Continue independent authorized work. Preserve completed tasks and their evidence; specifications own requirements and acceptance, while task documents own execution plans and results.

## Tailwind authoring preference

When the target uses Tailwind CSS, put this ongoing preference in its applicable AGENTS.md. Prefer utilities directly in markup `class` or JSX `className`. Do not extract CSS classes or `@apply` solely to shorten attributes. Preserve deliberate existing abstractions; shared components, conditional class helpers and custom CSS remain appropriate when needed. Inline refers to where classes are authored, not a requirement to keep an attribute on one physical line or to use a `style` attribute.

Keep conditional alternatives as complete utility strings rather than constructing fragments of class names. Detailed styling rationale may live in an existing project document linked from AGENTS.md, but the short preference must remain in AGENTS.md and work without an installed skill. Omit this guidance when Tailwind is absent; do not introduce Tailwind or alter lint configuration while adopting instructions.

## Verification and completion in the target

Run applicable formatting, lint, typecheck, real tests, builds and hook checks in the target. Verify behavior affected by the change; static compilation alone is insufficient for runtime claims. Record actual commands, results and limitations concisely in existing task evidence, or report directly when no task document exists. Include environment details only when relevant to understanding or reproducing results. Mark unexecuted checks as not run with reasons; an empty suite is not behavioral coverage.

Update selected task/index statuses consistently: TODO, IN_PROGRESS, BLOCKED or DONE. Respect task and phase dependencies; independent work may continue without bypassing a blocked prerequisite. Do not mark incomplete work DONE to hide a blocker.

Report changed files and purposes, verification, exclusions, blockers and the next action briefly. Link task evidence instead of repeating it; no separate report document or research table is required for routine work. Do not commit, create remotes, push or deploy without authorization. The skill source repository is documentation-only and does not execute these target-project checks.

## Planning, feedback and outcome gates

Use one agent sequentially. A selected playbook describes execution order; a skill describes how to perform a bounded operation. Neither is required for routine work once persistent target instructions exist. For a small fix, a short scope/acceptance/verification checklist is sufficient; do not manufacture phases or a second tracker.

Before implementation, review the authorized requirements against tasks or the small-work checklist. Include relevant nonfunctional needs, architecture/data flow, API/UI/state and failure paths. Check coverage, feasibility, conflicts, duplicate scope, dependency cycles/order, risks, observable acceptance and unresolved decisions. Record the Planning Quality Gate in existing tracking or report it directly. Material contradictions block affected tasks; continue independent authorized work.

Never change an ID that has ever left TODO for IN_PROGRESS, BLOCKED or DONE, even after returning to TODO. Preserve IDs when history is unknown; allocate new IDs without renumbering. Retain status transitions/reasons and split/merge/supersession links with original records/evidence. Supersession is not proof of completion or a satisfied dependency. Additional scope after DONE normally gets new linked tasks; correct an inaccurate DONE only with evidence and retain the original record.

When requirements are missing, tasks conflict, support constraints arise, design changes are needed or verification fails: identify location, cause and impact; compare specification and tasks; decide corrective/new work; obtain user decisions for changes outside approved requirements/architecture; then update coverage, dependencies and acceptance without resetting history. Recheck affected planning assumptions before dependent execution resumes. Safe refinements within authorization need no repeated approval.

For recurring mistakes, assess recurrence, impact and maintenance cost. Prefer prevention through architecture/API design, then static checks (such as lint/types), automated behavioral tests, runtime checks, and finally skill/AGENTS.md prose for judgment that cannot be encoded. Reuse existing checks; do not add a rule for every incident. In an adopting project, verify that a selected automated guard rejects a representative bad case and accepts a valid case, and includes intended files in normal checks/CI when present. Do not introduce tools merely to restate a rule or weaken checks to hide failures. Source maintenance here documents target safeguards without installing or running them.

At completion, conduct a separate Completion Gate from the original requirements and approved changes, not just DONE tasks. Compare actual behavior and evidence with acceptance, look for omitted requirements and unresolved material issues, and distinguish required checks from optional checks. Report COMPLETED only when requested requirements and mandatory verification are satisfied, PARTIAL when implementation or verification remains, or BLOCKED when a material issue prevents progress. State scope, exclusions, reasons, risks and next action. Failed, unexecuted or stale required checks cannot establish completion; approved deferrals remain explicit. Planning completion is not implementation completion.

## Context and session continuity

Read only the selected playbook, needed skill references and affected project areas. Reuse research and evidence while their versions, code and assumptions remain valid; recheck affected integration boundaries after changes. Token savings never justify omitting required verification.

For long work, update one concise checkpoint in existing tracking with current phase/task, next eligible action, decision/blocker links and verification links. Keep detailed status/results in their existing tasks rather than duplicating them in a session log. Before stopping, record incomplete changes and checks still needed. On resume, read applicable instructions, the checkpoint and relevant task/specification, inspect staged/unstaged changes, and reconcile changed assumptions/evidence before continuing. Do not reset tasks or repeat whole-project analysis by default.
