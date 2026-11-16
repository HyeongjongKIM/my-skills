# Phase queue

Use this index only when phased tracking is selected. Read the earliest phase that is not DONE and select its earliest task with completed dependencies. Do not advance past a blocked dependency or phase. Preserve completed phases and evidence.

| Phase                                     | Goal     | Dependencies             | Status |
| ----------------------------------------- | -------- | ------------------------ | ------ |
| [01 — {{PHASE_NAME}}](01-phase/README.md) | {{GOAL}} | {{DEPENDENCIES_OR_NONE}} | TODO   |

Statuses: TODO, IN_PROGRESS, BLOCKED, DONE. Mark a phase DONE only when all tasks are DONE or approved deferrals are explicitly recorded. Update this index when phase status changes; link tasks using their full phase path across phases.

Next action: {{NEXT_TASK_PATH_OR_BLOCKER}}.
