# Model routing in Codex and Claude Code

Use the [working rules](workflow.md#agent-efficiency-and-model-routing) to decide whether a different model, effort level or subagent is useful. The examples below are optional and relative to the adopting project's root. Each requires the corresponding host with support for the fields shown and access to the selected model. No project packages or plugins are required.

Check the active host, version, provider, available models, permissions and effective settings before applying an example. Inspect the relevant project configuration and account or organization overrides where accessible without exposing secrets. A new project setting or agent definition can shadow a user setting without editing the user's file. Preserve existing effective choices and restrictions unless the user authorizes the specific change. Report any conflict. Use built-in agents or session controls when they meet the need.

## Codex

### Primary session

In the interactive CLI, the user can select an available model and effort with `/model`. The CLI also accepts `--model` at launch. The top-level `model` and `model_reasoning_effort` in a trusted project's `.codex/config.toml` are defaults. Consult the config precedence for the installed host. Managed `[models.new_thread]` defaults, when present, take priority over ordinary project and user defaults for new threads unless explicitly overridden. Model and effort support depend on the client and account. Check the effective selection before proposing a setting. [Codex models](https://learn.chatgpt.com/docs/models), [config basics](https://learn.chatgpt.com/docs/config-file/config-basic), [configuration reference](https://learn.chatgpt.com/docs/config-file/config-reference).

In clients where Ultra enables proactive delegation, choose it only when delegation is authorized and compatible with the execution procedure. [Codex subagents](https://learn.chatgpt.com/docs/agent-configuration/subagents#triggering-subagent-workflows).

### Subagent settings

Current local Codex can spawn built-in or custom agents when asked or directed by applicable project or skill instructions and multi-agent tools are enabled. Custom agents use one TOML file per agent under `.codex/agents/` for the project or `~/.codex/agents/` for the user. Reuse suitable definitions and check the `name` field for collisions with existing agents. [Codex subagents](https://learn.chatgpt.com/docs/agent-configuration/subagents).

Codex resolves explicit spawn values first, then the respective `[agents]` defaults (`default_subagent_model` and `default_subagent_reasoning_effort`), then the parent values. If a spawn value or `[agents]` default selects a model and neither source provides an effort, Codex uses that model's default effort. A custom agent file's explicit values override the resolved settings. A file that sets only `model` keeps the previously resolved effort, so confirm compatibility or set both. [Codex subagents](https://developers.openai.com/codex/subagents), [configuration reference](https://learn.chatgpt.com/docs/config-file/config-reference).

Subagents inherit the parent's sandbox, approval policy, provider and MCP servers. A prose instruction to avoid edits does not enforce a read-only sandbox. [Codex subagent approvals and sandbox controls](https://learn.chatgpt.com/docs/agent-configuration/subagents#approvals-and-sandbox-controls).

### Optional Codex examples

In `.codex/config.toml`, add the following key to the existing `[agents]` table or add the table if absent. Use this example only when the target needs an explicit cap of two concurrently open subagent threads and the installed version supports the key. Preserve existing limits and check for the legacy `max_threads` alias before adding a limit. [Codex subagents](https://developers.openai.com/codex/subagents).

```toml
[agents]
max_concurrent_threads_per_session = 2
```

In `.codex/agents/scope_reviewer.toml`, use the following top-level fields for recurring, narrowly scoped source review when the built-in explorer is insufficient and the host supports the example model and effort. Select a supported pair for the actual workload. For Luna, the current Codex guidance starts at `high`. Use the file as a whole for a new role. For an existing role, add only missing, compatible fields and preserve its name and instructions. The agent definition works independently of the optional concurrency limit. [Codex subagents](https://learn.chatgpt.com/docs/agent-configuration/subagents#choosing-models-and-reasoning).

```toml
name = "scope_reviewer"
description = "Map the code paths and existing checks for a bounded change."
model = "gpt-6-luna"
model_reasoning_effort = "high"
developer_instructions = """
Inspect the assigned paths without editing files.
Return relevant file or symbol references, the checks you found, and any gaps.
"""
```

## Claude Code

### Primary session

The user can select a model with `/model` or `--model` and set effort with `/effort` or `--effort`. Interactive choices can persist to user settings, so use the documented session-only choice or launch flags for one-off work. Project defaults can live in `.claude/settings.json` using documented keys such as `model` and `effortLevel`. Effective values depend on settings precedence, the model, the provider and organization limits. For example, `ANTHROPIC_MODEL` can outrank the file's `model` at launch, and `CLAUDE_CODE_EFFORT_LEVEL` outranks interactive effort selections. [Claude Code model configuration](https://code.claude.com/docs/en/model-config), [settings precedence](https://code.claude.com/docs/en/settings).

Treat `opusplan` and automatic model fallback according to their own triggers. Ultracode can start workflows that delegate to subagents. Choose it only when delegation is authorized and compatible with the execution procedure. [Model configuration](https://code.claude.com/docs/en/model-config), [dynamic workflows](https://code.claude.com/docs/en/workflows).

### Subagent settings

Claude Code can delegate based on a subagent's description or an explicit request. Project agents are Markdown files with YAML frontmatter in `.claude/agents/`. For the same name, managed definitions rank above `--agents`, project and user definitions, in that order. Plugin agents have scoped names. Across nested project directories, the definition closest to the working directory wins. Within a single agent tree, keep names unique so discovery does not depend on filesystem read order. [Claude Code subagent scopes](https://code.claude.com/docs/en/sub-agents#choose-the-subagent-scope).

- **Model.** For ordinary custom subagents, a supported invocation model alias takes precedence over the file's `model`, then `CLAUDE_CODE_SUBAGENT_MODEL`, then the spawning conversation's model. An explicit `model: inherit` selects the spawning conversation's model. Full model IDs can be used in the file when the provider supports them. Managed allowlists and the supported `CLAUDE_CODE_SUBAGENT_MODEL_FORCE` override can change the effective model. Check the official rules for built-ins, forks and provider-specific alias resolution. [Claude Code subagent models](https://code.claude.com/docs/en/sub-agents#choose-a-model).
- **Effort.** On versions that support these controls, `CLAUDE_CODE_EFFORT_LEVEL` outranks invocation `effort` for a non-fork subagent, which outranks the agent file's `effort`. When neither invocation nor file sets it and there is no environment override, Claude Code checks applicable spawning-agent or turn effort and then `CLAUDE_CODE_SUBAGENT_EFFORT`. Otherwise the ordinary subagent uses session effort when it runs on the main session's model. A different model does not inherit that session selection. Available values and caps depend on the model and provider. Extended thinking settings inherit from the main conversation and are configured separately from per-agent effort. [Claude Code subagent effort](https://code.claude.com/docs/en/sub-agents#choose-an-effort-level), [model configuration](https://code.claude.com/docs/en/model-config#adjust-effort-level).

### Optional Claude Code example

In `.claude/agents/scope-reviewer.md`, use this YAML frontmatter at the start of the file and put the instructions below it. Use it for recurring bounded source review when the built-in Explore agent is insufficient and the active host and provider support the selected alias, effort and tools. The `tools` allowlist limits the role to file reads and searches. If the role already exists, add only missing, compatible fields to its frontmatter and merge any missing instructions into its body. Keep the description short because Claude Code loads it for agent selection. [Claude Code subagent configuration](https://code.claude.com/docs/en/sub-agents#configure-subagents).

```markdown
---
name: scope-reviewer
description: Map the code paths and existing checks for a bounded change.
tools: Read, Grep, Glob
model: sonnet
effort: low
---

Inspect the assigned paths without editing files.
Return relevant file or symbol references, the checks you found, and any gaps.
```

Subagent requests count toward the same usage limits as the primary session. Compare the benefit of keeping verbose work out of the primary context with the cost of the extra requests. Where available, use `/usage` to review session token usage or plan usage when assessing recurring workloads. [Claude Code subagents](https://code.claude.com/docs/en/sub-agents), [usage and costs](https://code.claude.com/docs/en/costs).

## Confirm target behavior

Review changed files for the intended scope and effective precedence. When target verification is authorized, load the project in the supported host, confirm the shared instructions and agent are discoverable, and check the effective model, effort and permissions on a bounded representative request. Codex CLI exposes agent activity in `/subagents`. Claude Code versions that expose model details in `/tasks` show the running subagent's model and any reported effort there. Use only the evidence the host exposes and report settings or behavior that could not be verified. These examples configure defaults or individual runs. Project instruction text supplies the routing criteria, and changing a subagent definition leaves the primary session's model selection intact.
