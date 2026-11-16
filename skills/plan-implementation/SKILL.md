---
name: plan-implementation
description: Turn project requirements into bounded phases and implementation tasks with dependencies, observable acceptance criteria and verification plans. Use to create or refine a phased task queue while preserving completed evidence; not to implement tasks, configure tooling or adopt project-wide agent instructions.
---

# Plan implementation

Read [planning guidance](references/planning.md). Use the bundled [task queue](templates/tasks/README.md), [phase index](templates/tasks/01-phase/README.md) and [task document](templates/tasks/01-phase/01-task.md) as source templates. Each link is relative to this skill; no sibling skill is required.

## Procedure

1. Read the user's requirements, applicable target instructions, README, specifications, architecture decisions and existing task documents. Inspect staged and unstaged Git changes and preserve unrelated work. Identify implemented behavior and completed evidence before proposing new work.
2. Define the requested outcome, scope, observable acceptance and explicit exclusions. Resolve details from available project context. Record material unanswered questions; do not invent product, deployment, package-manager or branch decisions.
3. Split work into meaningful phases and bounded tasks, using the target's existing tracking conventions where applicable. Make dependencies explicit with full paths across phases. Do not precreate empty future phases or bypass blocked prerequisites.
4. Write or merge task documents and indexes. Link specifications as the requirements source; a small task may state acceptance directly. Include concrete implementation steps and verification plans tied to behavior, actual target commands and working directories. Where a command or suite does not yet exist, state that gap instead of claiming verification.
5. Resolve all placeholders, rename example phase/task paths to concrete goals with numeric ordering, and update references. Review dependency order, acceptance coverage, statuses and links through reads/searches. New unimplemented work remains TODO or BLOCKED; planning completion does not make implementation DONE.

## Completion and boundaries

Deliver a usable queue, phase indexes and task plans, or merge equivalent information into existing tracking. Summarize the next eligible task, blockers, open decisions, changed files and review limits. Preserve completed work and meaningful evidence. Follow applicable target instructions throughout; this skill also works when no AGENTS.md exists. Do not implement the planned work, install tools, rewrite persistent instructions or run application checks merely to finish planning. Do not commit, create remotes, push or deploy without authorization.
