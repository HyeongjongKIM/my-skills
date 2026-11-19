---
name: plan-implementation
description: Turn project requirements into bounded phases and implementation tasks with dependencies, observable acceptance criteria and verification plans. Use to create or refine a phased task queue while preserving completed evidence; not to implement tasks, configure tooling or adopt project-wide agent instructions.
---

# Plan implementation

Read [planning guidance](references/planning.md). Use the bundled [task queue](templates/tasks/README.md), [phase index](templates/tasks/01-phase/README.md) and [task document](templates/tasks/01-phase/01-task.md) as source templates. Each link is relative to this skill; no sibling skill is required.

## Procedure

1. Read the user's requirements, applicable target instructions, README, specifications, architecture decisions and existing task documents. Inspect staged and unstaged Git changes and preserve unrelated work. Identify implemented behavior and completed evidence before proposing new work.
2. Define the requested outcome, scope, observable acceptance and explicit exclusions. Resolve details from available project context. Record material unanswered questions; do not invent product, deployment, package-manager or branch decisions.
3. Map every major requirement to tasks or existing implementation evidence, including relevant nonfunctional needs, architecture/data flow, API/UI/state and error paths. Record exclusions and open decisions explicitly; use a short checklist for small work. Split work into meaningful phases and bounded tasks, using the target's existing tracking conventions where applicable. Make dependencies explicit with full paths across phases. Do not precreate empty future phases or bypass blocked prerequisites.
4. Write or merge task documents and indexes. Link specifications as the requirements source; a small task may state acceptance directly. Include concrete implementation steps and verification plans tied to behavior, actual target commands and working directories. Where a command or suite does not yet exist, state that gap instead of claiming verification.
5. Apply the Planning Quality Gate in the bundled guidance: review coverage, feasibility, contradictions, duplicate scope, dependencies/cycles and observable acceptance against original requirements. Record findings with location, cause, impact and resolution; stop affected work for material contradictions, missing prerequisites or infeasible requirements; report evidence, impact and a proposed correction and obtain user approval before proceeding. Resolve all placeholders, rename example phase/task paths to concrete goals with numeric ordering, and update references. Review dependency order, acceptance coverage, statuses and links through reads/searches. New unimplemented work remains TODO or BLOCKED; planning completion does not make implementation DONE.
6. Preserve every task ID from creation without change or reuse, plus status history, cancelled records and split/merge/replacement references. Apply the bundled identity policy; on revisions recheck requirement coverage and dependencies. Reuse existing execution procedures for verification, completion and continuity. Only when needed, merge missing safeguards from the bundled queue contract into existing tracking; do not duplicate procedures or require this skill during implementation.

## Completion and boundaries

Deliver proportionate plans in existing tracking, a short checklist, or a queue with phase/task documents when needed. Summarize the next eligible task, blockers, open decisions, changed files and review limits. Preserve completed work and meaningful evidence. Follow applicable target instructions throughout; this skill also works when no AGENTS.md exists. Do not implement the planned work, install tools, rewrite persistent instructions or run application checks merely to finish planning. Do not commit, create remotes, push or deploy without authorization.
