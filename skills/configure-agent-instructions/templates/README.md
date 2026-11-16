# {{PROJECT_NAME}}

{{PROJECT_PURPOSE_AND_USERS}}

## Development

Use Node {{NODE_VERSION}} and {{PACKAGE_MANAGER_AND_VERSION}}. Install using {{INSTALL_COMMAND_WITH_LOCKFILE_POLICY}}.

| Script       | Command                              | Purpose                                               |
| ------------ | ------------------------------------ | ----------------------------------------------------- |
| format       | {{FORMAT_COMMAND}}                   | Format an explicit reviewed file list during adoption |
| format:check | {{FORMAT_CHECK_COMMAND}}             | Check style without writes                            |
| lint         | {{LINT_COMMAND}}                     | Static correctness checks                             |
| typecheck    | {{TYPECHECK_COMMAND}}                | Compiler/framework types                              |
| test         | {{TEST_COMMAND_OR_EXPLICIT_ABSENCE}} | Automated behavior checks                             |
| build        | {{BUILD_COMMAND}}                    | Verify deliverable output                             |

## Documents

- [Agent instructions](AGENTS.md): bounded implementation workflow.
- [Architecture](docs/architecture.md): optional; remove this link and describe simple boundaries here when no separate document is needed.
- Tooling: {{TOOLING_DOCUMENT_PATH_OR_SETTINGS_AND_COMMANDS_HERE}}. Link an existing document when useful; creating one is optional.
- Specification: {{SPECIFICATION_PATH_OR_TASK_ACCEPTANCE_SECTION}}
- Task tracking: {{TASK_QUEUE_PATH_OR_EXISTING_TRACKER_OR_NO_PLANNED_WORK}}

{{SETUP_ENVIRONMENT_AND_LIMITATIONS_WITHOUT_SECRETS}}
