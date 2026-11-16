# Planning phases and tasks

Use applicable target instructions and existing tracking conventions. Templates describe the default Markdown layout when creating a new phased queue; they do not require another skill or an AGENTS.md to exist.

## Structure and scope

Use `tasks/README.md`, meaningful numbered phase directories and a README in each phase. Rename `01-phase` and `01-task.md` for concrete goals and update links. Numeric ordering communicates execution order; dependencies determine eligibility. Do not precreate empty phases or move completed work merely to enforce naming. Follow the target's existing path conventions and retain conventional README.md and AGENTS.md names and tool-required paths.

A phase represents a coherent outcome. A task has a bounded behavior/change, allowed scope, explicit exclusions, dependencies, observable acceptance and a verification plan. Avoid a separate task for every tool or file when they form one verifiable change. Record dependencies across phases with full task paths and do not introduce cycles.

Specifications define requirements and acceptance criteria. Link them from tasks rather than creating conflicting copies; small tasks may state acceptance directly when no separate specification is necessary. Link existing architecture/tooling decisions only when relevant. Keep deployment, branches, workspace names, package managers and commit scopes as target decisions.

## Status and evidence

Statuses are TODO, IN_PROGRESS, BLOCKED and DONE. New implementation plans start TODO unless a concrete blocker applies. Planning a task is not implementing it. Preserve existing statuses and evidence unless available facts justify a correction; do not mark work DONE without acceptance and applicable verification. Approved deferrals remain explicit and never silently satisfy a blocked dependency.

Keep task, phase and queue statuses consistent. Select the earliest unfinished phase and earliest task with satisfied dependencies; independent work may proceed without bypassing a blocked prerequisite. A blocker records its exact constraint, impact and next action. Do not rewrite completed evidence to match a new plan.

Plan verification appropriate to affected behavior using actual target commands and working directories. Identify absent suites, unavailable environments and unresolved commands explicitly. Distinguish expected results from observed evidence; a build is not proof of runtime behavior and an empty suite is not coverage. Do not execute application verification during a planning-only request.

## Research and review

Follow applicable target instructions for support and research. When a plan chooses dependencies, external APIs or tool configuration, consult current official documentation for the installed/selected versions and relevant maintenance/security, engines and peers. Routine task prose needs no new research. If support cannot be established, block dependent work, explain exact constraints and supported alternatives, and continue independent planning. Do not force incompatible combinations, rely on private internals or weaken checks to hide failures.

Before handing off, read the queue, phase indexes and task documents together. Check requirement coverage, dependency order, status consistency, concrete next actions and resolved placeholders/paths through document reads and searches. Keep results concise; no separate report or research diary is required. Preserve meaningful dates and environment details only when they explain evidence.
