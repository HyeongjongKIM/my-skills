# Project development

Use for a new project or substantial development. Outcome: the authorized scope is implemented with evidence, or remaining work is explicitly PARTIAL/BLOCKED. Apply [gate criteria](gates.md); use existing target instructions and tracking.

1. Establish goals, users, original requirements, nonfunctional constraints, acceptance and exclusions. Resolve material product/architecture decisions instead of guessing.
2. Inspect existing code, Git changes, instructions, implemented behavior, architecture/data flow, commands and verification evidence. Preserve existing work and avoid duplicate tasks.
3. Create or refine requirement-linked phases/tasks with dependencies and verification plans. Use `plan-implementation` if available, keeping that invocation planning-only; return here to execute within the user's implementation authorization. Setup skills are optional only when tooling or persistent instructions actually need changes.
4. Apply the Planning Quality Gate. Repair gaps and block affected tasks for unresolved material contradictions; identify eligible independent work.
5. Implement one eligible bounded task at a time in dependency order. Verify its acceptance using applicable target checks and behavioral observations, record actual results and update task/index status. Do not bypass prerequisites or use planning as implementation evidence.
6. Apply the feedback procedure when implementation reveals missing scope, contradictions, constraints or failed tests. Preserve IDs and history and recheck affected dependencies/acceptance before continuing.
7. Compare the entire authorized requirement set with actual implementation and evidence, including scope the plan missed. Apply the Completion Gate; all tasks DONE is insufficient.
8. Report COMPLETED, PARTIAL or BLOCKED with evidence, exclusions, remaining work and next action. On interruption, update the existing checkpoint with phase/task, decisions, blockers and verification links so the next session can continue without a full repeat analysis.
