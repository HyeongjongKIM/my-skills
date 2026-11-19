# Bug fix

Use to correct a defect. Outcome: the observed defect is corrected with suitable regression evidence, or reproduction/verification limits remain explicit. Apply [gate criteria](gates.md) at bug scope; a short checklist in the current task or response normally suffices. Do not create phases or invoke a planning skill for a straightforward fix.

1. Read applicable instructions and Git changes. Establish symptoms, expected behavior, reproduction conditions, affected versions/environment and existing failure evidence. If reproduction is unavailable, state uncertainty and seek alternative evidence without inventing a confirmed cause.
2. Trace the cause and affected contracts; distinguish symptom from cause. Define the smallest coherent correction and observable acceptance. Apply a brief Planning Quality Gate to scope, risks, dependencies and the planned regression check. Use `plan-implementation` only when the fix actually needs decomposition.
3. Implement the correction without unrelated redesign. If evidence changes the diagnosis or expands scope, apply feedback and resolve material decisions before dependent work.
4. Where feasible, demonstrate the reproduction check failing before and passing after the fix. Otherwise perform an appropriate regression observation and explain the evidence limit. Check affected neighboring behavior; do not weaken tests to make the fix appear successful.
5. Apply the Completion Gate to the original symptom and expected behavior. Report cause, correction, actual regression results and limits as COMPLETED, PARTIAL or BLOCKED. For recurring errors, evaluate structural/automated prevention using applicable target instructions and the gate guidance rather than adding prose by default.
