# Selecting and customizing workflow documents

Templates are Markdown source documents. Merge selected content into the target, resolve every placeholder to a concrete value or explicit reason for absence, and remove unused sections and links. Preserve existing instructions, specifications, tasks and meaningful evidence.

| Template | Target role |
| --- | --- |
| [AGENTS.md](../templates/AGENTS.md) | Core project constraints, scope and actual command/document pointers |
| [README.md](../templates/README.md) | Current project state, purpose, setup, development commands, available skills and navigation |
| [Architecture](../templates/docs/architecture.md) | Optional current boundaries/data flow when README is insufficient; link ADRs for significant decision history when needed |

Start with existing project instructions and README content. Keep simple architecture and tooling decisions in README. Link an existing tooling document when useful. Remove unsupported command rows and describe absent checks honestly. Node-specific template fields apply only when the target uses Node.

Preserve the target's task tracker and completed evidence. If it uses phased Markdown tasks, link its queue and keep task/phase/index statuses consistent. If no tracker is needed, omit its link; do not create empty phases just to adopt instructions. Concrete requirements, phase decomposition and task generation belong to a separate planning request.

Apply the [document responsibilities](workflow.md#documentation-management) and [adoption checklist](workflow.md#procedure-ownership-and-safe-adoption) when merging existing guidance.

For skill installation and updates, follow the [skill documentation and update policy](workflow.md#skill-documentation-and-updates). Use the README's skill list for current availability and purpose, with relative links in its navigation to the actual project instructions and playbooks.

## Instruction discovery

Check the effective instruction chain from the directory where work runs. Keep existing project and user policies in place, and use the active project instruction file or an existing reference to a shared owner. Report conflicts or unsupported discovery paths before claiming that a change applies.

- **Codex.** From the project root through the current working directory, Codex reads at most one nonempty instruction file per directory, checking `AGENTS.override.md`, `AGENTS.md` and then configured fallback names. Account for more specific instructions and the combined document size limit. If an existing override or fallback owns the rules, preserve its scope and verify that the chosen file is loaded after the merge. In a directory without a detected project root, use the actual working directory for the check. [Codex instruction discovery](https://learn.chatgpt.com/docs/agent-configuration/agents-md#how-codex-discovers-guidance).
- **Claude Code.** Direct AGENTS.md loading depends on the installed release, Project instructions setting and whether a Claude instruction file is present in the working directory or an ancestor. A `CLAUDE.local.md` can also suppress direct loading under the default setting. Reuse a CLAUDE.md owner in Claude-only projects, or use a documented import when the project shares rules in AGENTS.md and Claude does not already load them. Claude's direct discovery does not cover Codex's `AGENTS.override.md`. Where available, inspect Memory files in `/context all`. [Claude Code project instructions](https://code.claude.com/docs/en/memory#when-claude-code-reads-agentsmd).

For a project that uses both hosts, keep one owner for shared rules. If adopting a shared AGENTS.md is in scope, preserve host-specific rules in their current files and connect each active instruction chain to the shared file. For example, a Codex override that masks a same-directory AGENTS.md can explicitly require reading it. Apply the Claude import below only where needed. If discovery differs by working directory, verify each affected entry point.

For the shared-file case, merge the following line into the adopting project's existing loaded `CLAUDE.md` next to its `AGENTS.md`, or create a minimal root `CLAUDE.md` there if required and authorized. Preserve Claude-specific content. If the files are in different directories, use the actual path relative to the importing file. Required packages: none. This import applies only when the host loads the importing file and supports imports.

```markdown
@AGENTS.md
```
