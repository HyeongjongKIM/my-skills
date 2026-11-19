# Phase queue

Use this index only when phased tracking is selected. Read the earliest phase that is not DONE and select its earliest task with completed dependencies. Do not advance past a blocked dependency or phase. Preserve completed phases and evidence.

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

Queue status describes execution progress, not project completion. Compare original requirements and approved changes with actual behavior and required verification before declaring COMPLETED. Record missing implementation/checks as PARTIAL, or a material constraint preventing progress as BLOCKED. Preserve deferred scope explicitly. Keep detailed evidence in tasks; update this checkpoint instead of creating another status file.

Never change an ID that has ever left TODO, even after returning to TODO. Preserve existing IDs if history is unknown; allocate new IDs without renumbering. Retain split/merged task records and links. Execution order follows dependencies, not ID sorting.
