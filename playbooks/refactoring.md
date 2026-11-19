# Refactoring

Use to improve structure while preserving agreed behavior and public contracts. Outcome: the scoped structural goal is reached with preservation evidence, or remaining risk/work is explicit. Apply [gate criteria](gates.md).

1. Read applicable instructions, relevant implementation, Git changes and existing evidence. Identify current observable behavior, public/API/data contracts, consumers and integration boundaries.
2. Define structural goals, allowed scope and exclusions. Establish behavior-preservation checks or useful baseline observations before changing code; document missing coverage. A deliberate behavior change requires an authorized requirement decision, not a silent refactoring assumption.
3. Plan verifiable steps with dependencies and acceptance; use `plan-implementation` for substantial work and a checklist for small work. Apply the Planning Quality Gate to feasibility, scope, contract risks and verification coverage.
4. Change one bounded unit at a time and run relevant regression checks. Preserve contracts and record evidence; update existing tracking. Apply feedback to unexpected constraints, missing coverage or failures before dependent steps.
5. Apply the Completion Gate to both the structural goal and original behavior/contracts, including affected consumers. Report outcome, changed boundaries, regression evidence, exclusions and unresolved risks. On interruption leave a concise checkpoint in existing tracking rather than creating a separate refactoring log.
