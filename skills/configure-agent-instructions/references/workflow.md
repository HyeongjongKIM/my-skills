# Working contract for an AI agent

The user's current request and the target's applicable instructions govern adoption. These preferences are a guide to deliberate integration, not permission to replace a project wholesale.

This guide owns the persistent working rules for the agent-instructions skill. The target [AGENTS template](../templates/AGENTS.md) carries core obligations and navigation into an adopting project; detailed procedures belong in existing execution/tracking documents. Tool configuration and concrete task planning are separate requests.

## Requirement levels

**Required** means a working safeguard or a condition needed for a selected setting to function. **Default preference** means apply when suitable and explain a conflict or exclusion. **Optional** means select only when the target uses the relevant technology or needs the document scale.

| Level | Preference | Purpose / condition |
| --- | --- | --- |
| Required | Preserve user work and use supported public APIs | All work |
| Default preference | English documents | Preserve deliberate existing language conventions unless changing them is in scope |
| Default preference | Conventional Commits | Scope vocabulary remains a target decision |
| Default preference | Inline Tailwind utility classes | Only when the target uses Tailwind CSS; preserve deliberate existing styling decisions |
| Optional | Phased task queue with phase/task indexes | Only when work scale warrants it; reuse existing tracking or a short checklist |

## Before editing the target

Read applicable project instructions, README, and the relevant specifications, configurations, dependencies and task evidence. In a Git project, inspect staged and unstaged changes. Identify already completed work. Select a bounded task with satisfied dependencies and preserve unrelated work and settings.

Consult current official documentation when adding/upgrading dependencies, changing tool/framework configuration, introducing or changing external API use, or when support/behavior is uncertain. Use the installed or selected version’s documentation; check maintenance/security, engines and peers for dependency changes. Reuse findings while their versions and applicability remain valid. Routine prose and local application changes need no new research unless they raise these questions. For new dependencies, select maintained, secure, compatible stable versions; no version or major is mandated. Preserve existing constraints and avoid unrelated upgrades. Record selected versions and retain the target lockfile. Historical examples are evidence, never installation defaults.

## During work

Make small changes within the selected scope. Use documented supported configurations. Do not depend on private APIs or undocumented internals, patch vendors arbitrarily, force incompatible installs or introduce workaround architectures to evade support constraints. Never weaken types, lint or tests, add broad ignores, unsafe casts or suppressions solely to conceal errors.

If support cannot be established, stop the dependent work and report the exact constraint, official sources and supported alternatives. Continue independent authorized work. Preserve completed tasks and their evidence; specifications own requirements and acceptance, while task documents own execution plans and results.

## Agent efficiency and model routing

Choose the most efficient available model and effort that can reliably implement and verify the work. Account for the model's capabilities and the tools and context the task requires. Consider total cost, including reasoning, tool calls, likely retries, context handoff, integration and verification, plus any subagent execution. A lower-priced model can cost more overall if it requires repeated attempts or greater review. Accuracy, implementation quality, security and required verification take precedence over token savings.

Assess complexity from requirement clarity, familiarity with the affected contracts, dependency coupling, state and failure modes, reversibility, and the risk and difficulty of verification. File count, code length and repository size are context only. A small permission change can need deep review, while a mechanical change across many files can be straightforward.

| Task | Initial reasoning effort |
| --- | --- |
| Simple code edits | Low |
| UI and style changes | Low |
| Clear test and lint fixes | Low |
| Routine feature implementation | Medium |
| Refactoring across modules | Medium |
| Complex debugging and state management | Medium or High |
| Architecture design | High |
| Complex dependency and task conflict analysis | High |

Use these starting points within the selected model's supported settings when it has no more specific guidance for the workload. Reassess if evidence reveals hidden coupling, uncertain causes, costly failure modes or a need for deeper multi-step reasoning. Increase effort or choose a more capable model where the host supports it and the expected benefit warrants the cost.

If the primary session needs a different setting, use or recommend its documented controls as permitted and carry forward relevant findings and constraints. Prefer session-scoped changes for one-off work. Changes that persist or modes that can start subagents require the applicable authorization. A subagent's settings apply to its own work.

### Subagent delegation

- Handle straightforward or tightly coupled work in the primary session. Delegate only when authorized and supported, and when specialist analysis, independent work or isolation of substantial tool output justifies the extra requests, context transfer and review cost. Use the fewest agents that provide a concrete benefit. Avoid nesting and limit concurrency to work that can proceed independently.
- Follow the target's task prerequisites and execution procedures. A routing decision leaves task ownership, dependency order, lifecycle and gates governed by those procedures. Respect any sequential execution requirement.
- Define a distinct question or deliverable, relevant paths, governing constraints and expected evidence for each delegate. Share known findings to avoid duplicate exploration. Make analysis assignments read-only. Give each editing assignment exclusive ownership of explicit paths for its duration, including against concurrent primary-agent edits. Serialize work that needs overlapping files.
- Ask for concise findings, relevant file or symbol references, changes, checks and unresolved risks. The primary agent resolves conflicts, integrates results and verifies affected behavior before claiming completion.

### Token and context management

- Start with applicable instructions and likely entry points. Use targeted search and bounded reads, expanding along the relevant call paths, dependencies or ownership boundaries as needed. Reuse findings and verification evidence while the code, versions, environment and assumptions still apply. Recheck affected integration boundaries after changes.
- Investigate a repeated failure before rerunning its check. Retry when a correction, changed condition or diagnostic purpose justifies it. Read and report the relevant parts of long outputs while retaining the failing command, root-cause evidence or uncertainty, exit status and verification result as applicable. Retrieve more context when excerpts are insufficient.
- Keep requirements, constraints, decisions and unresolved verification available through handoffs and context compaction. Follow existing evidence ownership below. Prefer concise, verifiable results and avoid repeating logs or task history in the completion summary.

## Documentation management

Keep document responsibilities distinct and make only the documentation changes needed for the authorized work.

- Maintain README.md as the entry point describing the project's current state. Revise relevant content when features change; do not append task completion logs, test execution results or dated work histories.
- Record task-specific implementation results and verification evidence in the corresponding task document. When no task document exists, report results directly rather than turning README.md into a task log.
- Maintain current progress and next actions in existing task management documents; link detailed task evidence instead of copying it.
- Reflect architecture changes in the current architecture document, or the existing README architecture section when no separate document is needed. Use ADRs when significant decisions need historical rationale; distinguish superseded decisions from the current design.
- Do not describe previous implementations or discarded designs as current behavior. Preserve meaningful historical task evidence in its owning document.
- Link information already owned by another document instead of duplicating it. Do not repeat Git-tracked change details in separate Markdown logs.

## Tailwind authoring preference

When the target uses Tailwind CSS, put this ongoing preference in its applicable project instructions. Prefer utilities directly in markup `class` or JSX `className`. Do not extract CSS classes or `@apply` solely to shorten attributes. Preserve deliberate existing abstractions; shared components, conditional class helpers and custom CSS remain appropriate when needed. Inline refers to where classes are authored, not a requirement to keep an attribute on one physical line or to use a `style` attribute.

Keep conditional alternatives as complete utility strings rather than constructing fragments of class names. Link any existing styling rationale from the active instructions and keep the short preference there after skill removal. Omit this guidance when Tailwind is absent; do not introduce Tailwind or alter lint configuration while adopting instructions.

## Verification and completion in the target

Run applicable formatting, lint, typecheck, real tests, builds and hook checks in the target. Verify behavior affected by the change; static compilation alone is insufficient for runtime claims. Record actual commands, results and limitations concisely in existing task evidence, or report directly when no task document exists. Include environment details only when relevant to understanding or reproducing results. Mark unexecuted checks as not run with reasons; an empty suite is not behavioral coverage.

Report changed files and purposes, verification, exclusions, blockers and the next action briefly. Link task evidence instead of repeating it; no separate report document or research table is required for routine work. Do not commit, create remotes, push or deploy without authorization. The skill source repository is documentation-only and does not execute these target-project checks.

## Procedure ownership and safe adoption

The active project instructions own always-applicable constraints and navigation. Use the target's existing playbook or task-management document as the primary owner of execution order, task lifecycle, gates and continuity. Planning methods belong in planning guidance; execution procedures must remain available during implementation without invoking a planning skill. No sibling skill, source-repository playbook or installed setup skill is a runtime prerequisite.

Before removing detailed rules from existing instructions, locate their target owner and preserve missing safeguards there. Link that owner from the project instructions with an explicit obligation to follow it. Reuse equivalent existing guidance, preserving its status vocabulary and layout; do not paste a second checklist beside it. If existing documents suffice, create nothing. If no procedural document is justified, keep the necessary short fallback in existing instructions and use the request's scope/acceptance/checklist with direct reporting. Keep procedural links within the target's accessible documents.

Use the following adoption checklist only to fill gaps in the chosen owner.

- **Planning:** compare original requirements with bounded tasks or a small checklist; check relevant nonfunctional needs, boundaries/data flow, API/UI/state/failure paths, observable acceptance, feasible verification, omissions, conflicts, duplicate scope, risks and dependency cycles/order. Record the review in existing tracking or report directly.
- **Identity and lifecycle:** every task ID is immutable from creation and must never be reused. Retain status transitions/reasons and evidence, including cancelled tasks. Splits, merges and replacements retain original records/IDs and predecessor/successor links; update dependents to actual replacement work. Supersession or cancellation does not establish DONE or satisfy a dependency. New scope receives new linked IDs; evidence-based status corrections retain prior history. Synchronize task/phase/queue progress using existing conventions; never invent completion to hide a blocker.
- **Material plan problems:** stop affected work for contradictions, missing prerequisites or infeasible requirements. Report location, evidence/cause, impact and proposed correction; obtain user approval before affected execution resumes. Revalidate affected requirement coverage, dependencies and acceptance after the correction. Safe refinements without a material problem may proceed within authorization; independent authorized work may continue.
- **Execution and completion:** use satisfied task and phase prerequisites; verify affected behavior with actual commands, preserving results and not-run reasons in task evidence or the response. Compare actual behavior/evidence with original requirements and approved changes, independently of DONE statuses. Report COMPLETED only with requirements and mandatory verification satisfied, PARTIAL for missing implementation/checks, or BLOCKED for a material constraint preventing progress. Keep approved deferrals explicit; a planning-only result is not implemented behavior.
- **Continuity:** for long work, keep one checkpoint in existing tracking with current work, next eligible action, decisions/blockers, incomplete changes and verification links. On resume, read applicable instructions, checkpoint and relevant requirements/tasks, inspect Git changes and reconcile stale assumptions/evidence before continuing. Do not reset records, create a second tracker or require whole-project rereads. For short work, direct reporting suffices.

Keep the material-problem stop/approval and honest-verification obligations explicit in the project instructions even when they link to detailed procedures. Do not mandate phases, playbooks or task files for small projects, or invent document paths and commands.

## Repeated-error prevention

For recurring mistakes, assess recurrence, impact and maintenance cost. Prefer prevention through architecture/API design, then static checks, automated behavioral tests, runtime checks, and finally prose for judgment that cannot be encoded. Reuse existing checks; do not add a rule for every incident. In an adopting project, verify selected automation against representative valid/invalid cases and normal checks/CI when present. Do not introduce tools merely to restate a rule or weaken checks to hide failures. Source maintenance here documents safeguards without running them.
