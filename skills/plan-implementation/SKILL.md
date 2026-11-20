---
name: plan-implementation
description: Turn project requirements into bounded phases and implementation tasks with dependencies, observable acceptance criteria and verification plans. Use to create or refine a phased task queue while preserving completed evidence; not to implement tasks, configure tooling or adopt project-wide agent instructions.
---

# Plan implementation

Read [planning guidance](references/planning.md). Reuse existing tracking or a short checklist where sufficient. Open the bundled [task queue](templates/tasks/README.md), [phase index](templates/tasks/01-phase/README.md) and [task document](templates/tasks/01-phase/01-task.md) only for a new phased queue or when filling a gap in existing tracking.

## Procedure

1. Read the user's requirements and applicable instructions, then the relevant README sections, specifications, architecture decisions and task records. Inspect staged and unstaged changes when the target uses Git. Identify implemented behavior and completed evidence. Before editing existing records, apply the [identity and history policy](references/planning.md#stable-identity-and-history).
2. Define the requested outcome, scope, observable acceptance and explicit exclusions. Resolve details from available project context. Record material unanswered questions; do not invent product, deployment, package-manager or branch decisions.
3. Map every major requirement to tasks or existing implementation evidence, including relevant nonfunctional needs, architecture/data flow, API/UI/state and error paths. Record exclusions and open decisions explicitly; use a short checklist for small work. Split work into meaningful phases and bounded tasks, using the target's existing tracking conventions where applicable. Make dependencies explicit with full paths across phases. Do not precreate empty future phases or bypass blocked prerequisites.
4. Write or merge task documents and indexes. Link specifications as the requirements source; a small task may state acceptance directly. Include concrete implementation steps and verification plans tied to behavior, actual target commands and working directories. Where a command or suite does not yet exist, state that gap instead of claiming verification.
5. Apply the [Planning Quality Gate](references/planning.md#requirement-coverage-and-planning-quality-gate) before handoff. Review changed records and their links, statuses and prerequisites through reads/searches. Resolve placeholders and rename only newly instantiated example paths to concrete goals. New unimplemented work remains TODO or BLOCKED.
6. Reuse existing execution procedures for verification, completion and continuity. When a gap exists, merge only the missing safeguards from the [queue contract](templates/tasks/README.md#execution-contract) into existing tracking so implementation can proceed without this skill.

## Completion and boundaries

Deliver proportionate plans in existing tracking, a short checklist, or a queue with phase/task documents when needed. Summarize the next eligible task, blockers, open decisions, changed files and review limits. Preserve completed work and meaningful evidence. Follow applicable target instructions throughout; this skill also works when no AGENTS.md exists. Do not implement the planned work, install tools, rewrite persistent instructions or run application checks merely to finish planning. Do not commit, create remotes, push or deploy without authorization.

When installing or updating this skill is in scope, follow the [skill documentation and update policy](references/planning.md#skill-documentation-and-updates).
