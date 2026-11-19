# Gate criteria

Apply these checks at the scale of the selected request. Record results in existing tracking or the response for small work; do not require a new report file. A distinct pass by the same agent compares source requirements with the plan or implementation. It is not independent-agent validation or executable enforcement.

## Planning Quality Gate

Before implementation, map original requirements to bounded tasks or a checklist, including existing implementation evidence and approved exclusions. Consider relevant nonfunctional needs, architecture/data flow, API/UI/state and error/recovery paths. Check observable acceptance and a feasible verification method for each requirement. Task count is not a quality target.

Inspect specification/task conflicts, duplicate scope, missing/circular dependencies, execution order, feasibility, technical risks, omitted scope and unresolved decisions. For each finding report location, cause, affected scope and proposed resolution. Repair the plan before calling it ready. Material unresolved contradictions block affected work; independent work with satisfied prerequisites can continue. Resolve material requirement/architecture changes with the user when outside authorization.

## Feedback during execution

After each bounded change, compare observations with acceptance. On omissions, contradictions, constraints, design changes, failed checks or recurring mistakes, analyze impact against specification/tasks and decide correction or new work. Preserve existing IDs/history, update coverage/dependencies/acceptance and repeat the affected planning review. Never change an ID that ever left TODO, even if returned to TODO; preserve IDs when history is unknown. Allocate new IDs without renumbering and retain split/merge records and references. New scope after DONE gets linked new work; evidence-based corrections retain historical results.

Use applicable target instructions for recurring-error prevention and support decisions. If absent, consider recurrence, impact and upkeep; prefer architecture/API improvements, static checks, automated tests, runtime checks, then prose for judgment. Reuse checks and verify selected guards with good/bad cases in the target. Do not introduce dependencies or new rules without a concrete need and authorization.

## Completion Gate

Re-read original requirements and approved changes independently of the task list. Compare actual implementation and observed evidence, including user-visible behavior, acceptance, required checks, integration/regression coverage and material unresolved issues. Find requirements omitted by planning; add missing work rather than treating all DONE as proof. Use target commands where available, record exact results and reasons for checks not run, and distinguish existing failures from regressions. A build or empty suite alone cannot prove behavior.

- COMPLETED: requested requirements and mandatory verification are satisfied with applicable evidence.
- PARTIAL: implementation or required verification remains incomplete, including a required check that failed, was not run or became stale.
- BLOCKED: a material issue prevents further progress on the requested outcome; identify the constraint and resolution needed. Individual blockers do not prevent independent authorized work.

Report agreed scope, implementation, evidence, exclusions/approved deferrals, unresolved issues, verification limits/risks and next action. Approved deferrals never mean those requirements were delivered. Planning-only completion must be labeled separately from implementation. Do not claim runtime verification from document review. Commit, push and deployment remain subject to user authorization; this playbook grants none.
