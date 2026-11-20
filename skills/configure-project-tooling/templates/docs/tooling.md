# Development tooling

Optional separate document: keep this information in README.md for a small project. Remove unused policy entries and link task evidence instead of duplicating it.

## Environment and commands

Runtime/framework: {{STACK_AND_RUNTIME_VERSION}}. Package manager: {{MANAGER_VERSION}}. Lockfile: {{LOCKFILE_PATH}}.

{{EXACT_FORMAT_FORMAT_CHECK_LINT_TYPECHECK_TEST_BUILD_COMMANDS_AND_WORKING_DIRECTORIES}}

Record selected tool versions here only when they clarify a compatibility decision; manifests and the lockfile remain the dependency record.

## Project settings

- ESLint presets, typed rules and tsconfig coverage: {{LINT_POLICY_AND_TSCONFIG_BOUNDARIES}}
- Formatting scope/options and generated-file ignores: {{FORMAT_POLICY}}
- Source filename lint scope and rule-specific exceptions: {{FILENAME_RULE_SCOPE_AND_EXCEPTIONS_OR_NONE}}
- Runtime globals: {{FILE_SCOPED_GLOBALS_OR_NONE}}
- Optional framework/editor integrations: {{SELECTED_INTEGRATIONS_OR_NONE}}
- Optional hooks, commit checks and CI: {{SELECTED_AUTOMATION_OR_NONE}}
- Version updates and frozen installation: {{UPDATE_AND_INSTALL_POLICY}}
- Exclusions and reasons: {{EXCLUDED_SETTINGS_AND_REASONS_OR_NONE}}

## Decisions and verification

Follow applicable target instructions for when official research is needed. For dependency, configuration or external API changes and uncertain support, consult current official documentation for the selected versions, including maintenance/security, engines and peers where relevant. Record significant compatibility decisions with the relevant version and official link; omit this entry when none is needed.

{{COMPATIBILITY_DECISIONS_AND_OFFICIAL_LINKS_OR_NONE}}

{{TASK_EVIDENCE_LINK_IF_AVAILABLE}}

Keep enduring verification limitations and unresolved tooling decisions here when they affect normal development. Report task-specific commands, results and checks not run in task evidence or directly in the handoff. Distinguish official support from local build/typecheck and runtime evidence.
