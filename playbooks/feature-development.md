# Feature development

Use to add a feature to an existing project. Outcome: the feature satisfies its contract with relevant regression evidence, or remaining work is explicit. Apply [gate criteria](gates.md).

1. Read applicable instructions, the request, relevant architecture/code, Git changes and existing evidence. Identify affected boundaries, consumers, data/state flow and existing behavior to preserve.
2. Plan bounded requirement-linked tasks with dependencies, observable acceptance and verification. Use `plan-implementation` when decomposition is useful; a small feature can use an existing task/checklist. Identify API/UI/state/error paths and relevant nonfunctional needs.
3. Apply the Planning Quality Gate to feature scope and integration risks. Resolve or block material conflicts before affected implementation.
4. Implement sequentially with satisfied prerequisites. Run feature checks and relevant regression checks for existing consumers/integration boundaries; record actual evidence before DONE.
5. Apply feedback when new scope, contradictions or failed checks appear. Keep completed records and IDs; add linked work rather than resetting completed tasks.
6. Apply the Completion Gate against the feature's original requirements and approved changes, not only its task list. Report outcome, behavior changed, regression evidence, limits and remaining work. Update the existing checkpoint if interrupted.
