# Phase queue

Use this index only when phased tracking is selected. Read the earliest phase that is not DONE and select its earliest task with completed dependencies. Do not bypass a blocked task or phase prerequisite. If this phase has no eligible work, an independent task in another phase may proceed only when all its task and phase prerequisites are satisfied. Preserve completed phases and evidence.

| Phase                                     | Goal     | Dependencies             | Status |
| ----------------------------------------- | -------- | ------------------------ | ------ |
| [01 — {{PHASE_NAME}}](01-phase/README.md) | {{GOAL}} | {{DEPENDENCIES_OR_NONE}} | TODO   |

Statuses: TODO, IN_PROGRESS, BLOCKED, DONE. Mark a phase DONE only when all tasks are DONE or approved deferrals are explicitly recorded. Update this index when phase status changes; link tasks using their full phase path across phases.

## Requirement coverage

Use existing specification anchors or stable requirement labels. Replace this example row; a small queue may use a checklist instead.

| Requirement / source | Task IDs or existing implementation | Acceptance / verification link | Gap / decision |
| --- | --- | --- | --- |
| {{REQUIREMENT_ANCHOR}} | {{TASK_IDS_OR_EVIDENCE}} | {{CRITERION_AND_CHECK}} | {{NONE_OR_UNRESOLVED}} |

## Gates and current checkpoint

- Planning Quality Gate: {{REVIEWED_COVERAGE_CONSISTENCY_FEASIBILITY_AND_BLOCKERS_OR_NOT_REVIEWED}}
- Current phase/task and next eligible action: {{PATHS_AND_ACTION}}
- Decisions / blockers / verification: {{LINKS_OR_NONE}}
- Completion Gate: {{NOT_ASSESSED_OR_COMPLETED_PARTIAL_BLOCKED_WITH_SCOPE_AND_EVIDENCE}}

## Execution contract

Use the project's existing execution/playbook and task-management procedures as the primary owner: {{EXISTING_PROCEDURE_LINKS_OR_CONTRACT_BELOW}}. If those procedures cover the following safeguards, keep their links and omit duplicate details below. Otherwise merge missing rules here. This contract remains available to implementers without an installed planning skill; it does not authorize implementation beyond the user's request.

### Identity and lifecycle

Every task ID is immutable from creation and must never be changed or reused, including TODO and cancelled tasks. Allocate collision-free IDs without renumbering. Keep status transitions and reasons in the original task record. Preserve the existing status vocabulary; record cancellation/supersession as a disposition when no corresponding status exists. Cancellation, splitting, merging or replacement retains original IDs, history, evidence and predecessor/successor links. Update dependents to actual replacement work; cancellation/supersession never fabricates DONE or satisfies prerequisites. New scope after DONE gets linked new IDs; evidence-based status corrections retain historical results. Execution order follows dependencies, not ID sorting.

### Feedback and synchronization

Record evidence/status in the task first, then synchronize affected phase and queue indexes. Do not mark incomplete work DONE. For material contradictions, missing prerequisites or infeasible requirements, stop affected work; report location, evidence, impact and a proposed correction and obtain user approval before proceeding. Revalidate affected requirement coverage, dependencies and acceptance after changes. Independent authorized work with satisfied prerequisites can continue.

### Verification and Completion Gate

Verify affected behavior using actual target commands and working directories. Tasks own actual commands, observations, limitations and not-run reasons; link them here instead of copying results. Distinguish existing failures from regressions. A build or empty test suite alone is not behavioral evidence.

Queue status describes execution progress, not requirement completion. Re-read original requirements and approved changes independently of DONE tasks; compare actual behavior, acceptance and required verification, including omitted requirements and unresolved material issues. Add missing work with new IDs. Report COMPLETED only when requested requirements and mandatory verification are satisfied, PARTIAL for missing implementation or failed/unrun/stale required checks, or BLOCKED when a material constraint prevents progress. Name agreed scope, explicit deferrals, evidence, risks and next action. Deferrals do not imply delivery; planning completion is separate from implementation completion.

### Checkpoint and resume

For long work, update the single checkpoint above with current phase/task, next eligible action, decision/blocker and verification links, incomplete changes and outstanding checks. Keep detailed results/history in tasks. On resume read applicable instructions, checkpoint and relevant specification/tasks, inspect staged/unstaged Git changes, reconcile changed dependencies/decisions and stale evidence, then select eligible work. Preserve records; do not create a second tracker or repeat whole-project analysis by default.
