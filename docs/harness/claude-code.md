# Claude Code harness

Use the same English skill contents and [playbooks](../../playbooks/README.md); keep common working rules in the target's shared instructions.

- For local terminal use, copy selected complete skill folders to `.claude/skills/<skill-name>/`. Invoke `/plan-implementation` when installed. Codex's `.agents/skills` location and `$` selection syntax are not assumed here. See [official skill discovery and invocation](https://code.claude.com/docs/en/skills). Managed policies and cloud sessions can have different discovery rules; confirm the actual host rather than assuming a local folder is loaded everywhere.
- Confirm which project instructions the installed version/session loads. Current Claude Code documents conditional AGENTS.md discovery; existing CLAUDE.md, host version and settings can affect it. If AGENTS.md is not loaded, use the documented import below instead of copying common rules. See [official project instruction guidance](https://code.claude.com/docs/en/memory).

Target file: the adopting project's root `CLAUDE.md`, alongside its shared `AGENTS.md`. Merge this line only when shared instructions are not already loaded; preserve existing Claude-specific content. Required packages: none. Confirm the referenced file exists.

```markdown
@AGENTS.md
```

- Give the selected playbook's real file path in the request, for example: “Read docs/playbooks/feature-development.md and execute it for this feature; use /plan-implementation if decomposition is needed.” Playbook Markdown is not automatically registered as a Claude command.
- Use the available file/search/command tools under the host's permissions. Tool names, approval behavior and sandbox/network access differ from Codex. No tool equivalence, automatic installation or missing verification capability is promised. Record actual results and limits in existing tracking.

The common resume/checkpoint and gate procedures remain those of the playbook and target instructions. No Claude-specific agents, hooks, orchestration or runtime packages are added by this repository.
