# {{PROJECT_NAME}}

{{PROJECT_PURPOSE_AND_USERS}}

## Development

Use {{ACTUAL_RUNTIME_AND_TOOL_VERSIONS_WHEN_APPLICABLE}}. Setup: {{ACTUAL_SETUP_COMMANDS_AND_LOCKFILE_POLICY_OR_NO_SETUP_REQUIRED}}. Remove inapplicable command rows.

| Script       | Command                              | Purpose                                               |
| ------------ | ------------------------------------ | ----------------------------------------------------- |
| format       | {{FORMAT_COMMAND}}                   | Format an explicit reviewed file list during adoption |
| format:check | {{FORMAT_CHECK_COMMAND}}             | Check style without writes                            |
| lint         | {{LINT_COMMAND}}                     | Static correctness checks                             |
| typecheck    | {{TYPECHECK_COMMAND}}                | Compiler/framework types                              |
| test         | {{TEST_COMMAND_OR_EXPLICIT_ABSENCE}} | Automated behavior checks                             |
| build        | {{BUILD_COMMAND}}                    | Verify deliverable output                             |

## Documents

Merge navigation into existing sections; keep only links to actual documents. Do not create documents merely to fill this list.

- [Agent instructions](AGENTS.md): core project rules and procedure navigation.
- [Architecture](docs/architecture.md): optional; remove this link and describe simple boundaries here when no separate document is needed.
- Tooling: {{TOOLING_DOCUMENT_PATH_OR_SETTINGS_AND_COMMANDS_HERE}}. Link an existing document when useful; creating one is optional.
- Specification: {{SPECIFICATION_PATH_OR_TASK_ACCEPTANCE_SECTION}}
- Execution procedures: {{EXISTING_PLAYBOOK_OR_TASK_MANAGEMENT_PATH_OR_OMIT}}
- Task tracking: {{TASK_QUEUE_PATH_OR_EXISTING_TRACKER_OR_NO_PLANNED_WORK}}

{{SETUP_ENVIRONMENT_AND_LIMITATIONS_WITHOUT_SECRETS}}
