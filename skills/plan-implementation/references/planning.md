# Planning phases and tasks

Use applicable target instructions and existing tracking conventions. Templates describe the default Markdown layout when creating a new phased queue; they do not require another skill or an AGENTS.md to exist.

## Structure and scope

Reuse existing tracking first. For small work, a scope/acceptance/verification checklist suffices; no phases or additional task files are required. Only when a new phased queue is useful, use `tasks/README.md`, meaningful numbered phase directories and a README in each phase. Rename `01-phase` and `01-task.md` for concrete goals and update links. Numeric prefixes describe initial presentation order; dependencies determine execution eligibility. Never renumber existing IDs to express a new order. Do not precreate empty phases or move completed work merely to enforce naming. Follow the target's existing path conventions and retain conventional README.md and AGENTS.md names and tool-required paths.

A phase represents a coherent outcome. A task has a bounded behavior/change, allowed scope, explicit exclusions, dependencies, observable acceptance and a verification plan. Avoid a separate task for every tool or file when they form one verifiable change. Record dependencies across phases with full task paths and do not introduce cycles.

Specifications define requirements and acceptance criteria. Link them from tasks rather than creating conflicting copies; small tasks may state acceptance directly when no separate specification is necessary. Link existing architecture/tooling decisions only when relevant. Keep deployment, branches, workspace names, package managers and commit scopes as target decisions.

## Status and evidence

Statuses are TODO, IN_PROGRESS, BLOCKED and DONE. New implementation plans start TODO unless a concrete blocker applies. Planning a task is not implementing it. Preserve existing statuses and evidence unless available facts justify a correction; do not mark work DONE without acceptance and applicable verification. Approved deferrals remain explicit and never silently satisfy a blocked dependency.

Keep task, phase and queue statuses consistent. Select the earliest unfinished phase and earliest task with satisfied dependencies; if it has no eligible work, independent work in another phase may proceed only with all task and phase prerequisites satisfied. A blocker records its exact constraint, impact and next action. Do not rewrite completed evidence to match a new plan.

Plan verification appropriate to affected behavior using actual target commands and working directories. Identify absent suites, unavailable environments and unresolved commands explicitly. Distinguish expected results from observed evidence; a build is not proof of runtime behavior and an empty suite is not coverage. Do not execute application verification during a planning-only request.

## Research and review

Follow applicable target instructions for support and research. When a plan chooses dependencies, external APIs or tool configuration, consult current official documentation for the installed/selected versions and relevant maintenance/security, engines and peers. Routine task prose needs no new research. If support cannot be established, block dependent work, explain exact constraints and supported alternatives, and continue independent planning. Do not force incompatible combinations, rely on private internals or weaken checks to hide failures.

Before handing off, read the queue, phase indexes and task documents together. Check requirement coverage, dependency order, status consistency, concrete next actions and resolved placeholders/paths through document reads and searches. Keep results concise; no separate report or research diary is required. Preserve meaningful dates and environment details only when they explain evidence.

## Requirement coverage and Planning Quality Gate

Start from the original request and authoritative specifications, not just the proposed tasks. Give major requirements stable labels or existing specification anchors. In the existing queue or specification, map each requirement to task IDs, observable acceptance and planned verification. Include already implemented requirements with evidence links, explicit exclusions with authorization, and unresolved items; an unmapped requirement is a planning gap. Small work can use a short checklist instead of a matrix. Task count is not a quality metric.

Consider functional and relevant nonfunctional requirements (security, accessibility, performance, reliability and compatibility). Review architecture, boundaries and data flow; cover API contracts, UI, state ownership/transitions, persistence, migrations and failure/recovery paths where applicable. Mark irrelevant dimensions with a short reason rather than creating artificial tasks.

Before implementation, perform a distinct review against the source requirements. Check missing coverage, specification/task disagreement, conflicting tasks, duplicate scope, missing or circular dependencies, invalid order, ambiguous acceptance, feasibility, technical risks and unresolved design decisions. Each criterion must identify an observable result and a way to verify it; “implement correctly” is insufficient. Trace dependencies until each chain reaches a satisfied prerequisite or a concrete blocker.

Record the gate result and remaining findings in existing tracking, or report directly for a small checklist. Report each finding's location, cause, affected requirements/tasks and proposed resolution. Repair incomplete plans before declaring them ready. A material unresolved contradiction makes affected tasks BLOCKED; independent tasks with satisfied dependencies may proceed. For material contradictions, missing prerequisites or infeasible requirements, stop affected work and obtain user approval of the reported evidence, impact and proposed correction before proceeding. Do not silently choose a new requirement or architecture. A planning gate reviews the plan, not application behavior.

## Stable identity and history

Every task ID is immutable from creation and must never be changed or reused, including TODO and cancelled tasks. Allocate collision-free new IDs; never renumber existing tasks. Keep identity separate from display/execution order, and retain referenced paths where possible.

Record meaningful status transitions in the task's existing evidence/history section, including the reason. Retain cancelled records and their history; cancellation does not release an ID for reuse. Do not reset statuses or delete completed results to simplify a plan. On split or merge, preserve the original task record and ID with links to successors/predecessors and retained evidence. Prefer a retained superseded record to deletion; use a disposition note within the existing status vocabulary, and do not fabricate DONE or satisfy a dependency merely because work was superseded. Update dependents to the actual replacement tasks. Preserve existing references or a redirect if an authorized path move is unavoidable.

## Continuous planning and handoff

When omissions, contradictions, technical constraints, design changes or failed checks appear, locate the cause and impact, compare against the specification/tasks, and decide whether correction or additional work is needed. For material contradictions, missing prerequisites or infeasible requirements, stop affected work, report evidence, impact and a proposed correction, and obtain user approval before proceeding. Safe refinements without such a problem can proceed within authorization. Preserve IDs/history while updating coverage, dependencies and acceptance; rerun the affected planning review before dependent execution resumes.

New requirements after DONE normally get new task IDs linked to completed work. If evidence disproves an earlier completion, record that fact and a justified status correction without erasing the original evidence. New scope alone does not invalidate historical completion.

Hand off execution to the target's existing playbook/task-management procedure. If no sufficient owner exists and phased tracking is selected, adapt the bundled [queue execution contract](../templates/tasks/README.md#execution-contract) into the queue; merge only missing guidance and retain a pointer to any existing owner. It owns runtime verification, Completion Gate, synchronization and resume, so implementers do not need this skill installed. Do not create a queue merely to host procedures for small work; use a short checklist and direct reporting.

## Completion is separate from queue status

DONE tasks alone do not establish requirement completion. Planning completion means a reviewed plan, with implementation still TODO or BLOCKED as appropriate. The execution owner performs the actual Completion Gate against original requirements and observed evidence; see the bundled queue contract when no existing procedure suffices. A planning-only request does not run application checks or claim implementation completion.
