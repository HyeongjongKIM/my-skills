# Codex harness

Codex is the default host. Follow the shared [playbook entry](../../playbooks/README.md) for execution; this page only covers host integration.

- Local project skills: copy selected complete skill folders to `.agents/skills/<skill-name>/`. Keep bundled references/templates. Use `/skills` or `$plan-implementation` in Codex CLI/IDE to select an available skill. Restart if discovery has not refreshed. See [official skills documentation](https://learn.chatgpt.com/docs/build-skills).
- Persistent instructions: use the target's applicable `AGENTS.md` and any more specific instructions, following [Codex instruction discovery](https://learn.chatgpt.com/docs/agent-configuration/agents-md). Adopting this source repository does not automatically install instructions in another project.
- Playbooks: provide the chosen Markdown file's accessible path in the request. They are not registered slash commands. For example: “Read docs/playbooks/project-development.md and execute it for these requirements. Use $plan-implementation for the planning step, then implement the authorized tasks.” This example assumes that is the target's chosen copy location.
- Tools: use the actual host's file, search and command tools in the target working directory. Permissions, network access and available integrations vary by session. A playbook does not bypass approvals or supply missing tools. Record unavailable verification and remaining risks; do not claim a command ran because it was planned.
- Resume: start from the existing queue checkpoint and Git changes as described by the selected playbook. Chat history or an in-memory plan is not a durable substitute for project evidence.

No plugin manifest, subagent configuration, background runner or cross-host tool-name mapping is supplied. Skill discovery and runtime behavior in a particular installed host must be confirmed there; document review alone does not establish them.
