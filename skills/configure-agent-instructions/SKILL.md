---
name: configure-agent-instructions
description: Introduce or refine persistent AI-agent working instructions and project document navigation. Use when adopting an AGENTS.md workflow, support safeguards and verification reporting; not for configuring development tools or generating concrete feature task plans.
---

# Configure agent instructions

Read [working rules](references/workflow.md) and [document selection](references/documents.md). Adapt the bundled [AGENTS.md](templates/AGENTS.md), [README](templates/README.md) and optional [architecture document](templates/docs/architecture.md) to the target. Templates are source material, not mandatory files to overwrite.

## Procedure

1. Read applicable instructions, README, specifications, existing task tracking and completed evidence. Inspect staged and unstaged Git changes. Identify actual development commands, document locations, runtime and package manager without installing or changing tooling.
2. Determine what persistent instructions and navigation are missing. Preserve existing project decisions and instruction precedence. Merge proportionate planning/completion gates, stable task identity/history, feedback and resume safeguards, repeated-error prevention, bounded-work rules, user-work preservation, supported-API/research safeguards, applicable verification and concise completion reporting into the target AGENTS.md. When Tailwind CSS is used, include the inline utility preference from the working rules. Merge into the applicable existing AGENTS.md, or create a minimal target AGENTS.md when absent; omit Tailwind guidance for other stacks.
3. Keep instructions concrete. Replace every placeholder with target values or an explicit reason for absence. Reference actual commands; never invent passing checks or nonexistent scripts. Keep deployment, branches, workspace names, package manager and commit scopes as target decisions.
4. Apply the document responsibilities in the working rules to the target AGENTS.md. Keep README as a current-state entry point, linking existing architecture, tooling and task documents instead of duplicating their content. Keep simple architecture and tooling information there when no separate document is needed. Create a separate architecture document only when useful; use ADRs only when significant decisions need historical rationale. Preserve existing task tracking, completed tasks and meaningful evidence in their owning documents. If no concrete work is planned, state that rather than creating empty phases or requiring nonexistent indexes.
5. Review instruction consistency, resolved placeholders and local document references through reads/searches. This skill changes guidance only; run target executable checks only when the actual authorized change requires them. Distinguish document review from behavioral verification.

## Completion and boundaries

Deliver customized persistent instructions and useful navigation, with no dependency on this skill remaining installed. Report changed files, exclusions, unresolved project decisions and review limits. Record the source skill/repository reference with full SHA, or identify an uncommitted local path. Do not configure lint/format/hooks, install dependencies or turn requirements into feature tasks under this request. Those are separate tasks unless the user also requests them. Do not commit, create remotes, push or deploy without authorization.
