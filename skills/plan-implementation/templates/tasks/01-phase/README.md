# 01 — {{PHASE_NAME}}

Goal: {{PHASE_GOAL}}
Status: TODO
Dependencies: {{PHASE_DEPENDENCIES_OR_NONE}}
Specification: {{SPECIFICATION_PATH}}

| Order / task                     | Dependency                    | Status |
| -------------------------------- | ----------------------------- | ------ |
| [01 — {{TASK_NAME}}](01-task.md) | {{TASK_DEPENDENCIES_OR_NONE}} | TODO   |

Select the earliest unfinished task whose dependencies are DONE. Allocate collision-free IDs within this phase without renumbering existing tasks; refer to other phases by full path. A blocked dependency prevents dependent work. Update this table after recording task evidence and update the queue when this phase's status changes.

Completion: {{PHASE_ACCEPTANCE_AND_REQUIRED_VERIFICATION}}
Blockers / approved deferrals: {{LINKS_OR_NONE}}

Phase DONE describes phase progress only; use the queue Completion Gate to assess the requested outcome against requirements and observed verification.
