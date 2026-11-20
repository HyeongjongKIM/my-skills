---
name: configure-agent-instructions
description: Set up or revise persistent project instructions for coding agents, such as AGENTS.md or CLAUDE.md, and their links to project procedures. Use for project-level working rules, including model routing and delegation. Development tooling and concrete implementation plans are separate requests.
---

# Configure agent instructions

Read [working rules](references/workflow.md). Use the [AGENTS.md template](templates/AGENTS.md) as source material for the active project instructions. Read [document selection](references/documents.md) when changing README or architecture navigation, and open the [README](templates/README.md) or [architecture template](templates/docs/architecture.md) only if needed.

## Procedure

1. Read applicable instructions, README, and the specifications, task records and evidence relevant to the requested policy change. Inspect staged and unstaged changes when the target uses Git. Identify actual development commands, document locations and active coding hosts from the target and the user's setup. For Codex or Claude Code, check [instruction discovery](references/documents.md#instruction-discovery) before deciding where to write. Preserve project and user settings.
2. Identify the missing rules and their owners. Merge core working rules into the existing project instruction file that the active host loads. If no owner exists, use a minimal AGENTS.md for Codex or shared use, or CLAUDE.md for a Claude-only project that uses it. Preserve instruction precedence and keep Tailwind guidance only for targets using it.
3. Keep instructions concrete. Replace every placeholder with target values or an explicit reason for absence. Reference actual commands; never invent passing checks or nonexistent scripts. Keep deployment, branches, workspace names, package manager and commit scopes as target decisions.
4. Apply the [document responsibilities](references/workflow.md#documentation-management) and [adoption checklist](references/workflow.md#procedure-ownership-and-safe-adoption) before shortening instructions or moving a safeguard. Link the owning target procedure with an obligation to follow it. Reuse existing tracking and preserve completed evidence. For small projects with no procedure document, retain a concise actionable fallback in the project instructions.
5. Tailor the [agent efficiency policy](references/workflow.md#agent-efficiency-and-model-routing) to the target's work and verification cost. Read the applicable section of the [model routing reference](references/model-routing.md) only when advising on or changing host-specific routing. Propose or minimally merge project-scoped configuration when there is a concrete need, support is confirmed and the request authorizes it. Preserve effective settings and report conflicts or unsupported options.
6. Compare original and revised instructions for safeguard coverage, duplicate ownership, resolved placeholders and valid procedure links. Ensure procedures remain accessible without installed skills. Confirm instruction discovery from the affected working directory and any changed effective agent settings when a host check is available and authorized. Report any discovery or configuration that was reviewed only in the documents.

## Completion and boundaries

Deliver customized persistent instructions and useful navigation, with no dependency on this skill remaining installed. Report changed files, routing and delegation decisions, optional settings applied or omitted, unresolved project decisions and review limits. Record the source skill/repository reference with full SHA, or identify an uncommitted local path. Do not configure lint/format/hooks, install dependencies or turn requirements into feature tasks under this request. Those are separate tasks unless the user also requests them. Do not commit, create remotes, push or deploy without authorization.
