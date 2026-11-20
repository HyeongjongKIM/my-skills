# Adopting the preferences

Read the procedure and safeguards in [SKILL.md](../SKILL.md) first. Apply tooling changes in the actual target repository; this source repository supplies no installer, automatic updates, executable presets or validation fixtures.

## Version and support policy

This repository standardizes preferences, not package versions or majors. Do not interpret a code snippet's current API shape as a permanent release requirement. At adoption, check official versioned docs, maintained releases, security advisories, runtime engines, package-manager support and peer dependencies for every selected integration. Use [official entry points](official-sources.md), then follow the relevant release and advisory sources.

For new projects prefer currently supported stable combinations with relevant security fixes. Do not blindly install the latest major or downgrade to unsupported versions to reproduce old examples. In existing projects investigate current constraints first and avoid unrelated upgrades. Historical reference/validation versions are evidence only, never installation defaults.

If a rule, key or export changed, map its intent to the current officially supported API. Do not force incompatible installations, ignore peers or assume compilation establishes support. If no supported combination exists, name the conflicting packages/ranges/APIs, cite the sources and offer supported alternatives before proceeding with that integration.

The target records selected versions, runtime and manager decisions, and manages its lockfile for reproducibility. Use its frozen/immutable installation policy in CI. These local version constraints are distinct from this guide's version-neutral policy. Do not transfer reference overrides or automatically apply broad security fixes; report findings and unexecuted security checks accurately.

## Skill documentation and updates

When installing or updating this skill, keep the target README's list of available skills and their purposes current, with relative links to the project's own instructions, playbooks and related documents. Record the source repository name, URL, commit SHA or tag only when the user requests source tracking or the target rules require it. Use the designated location for the requested or required details. An authorized Git commit message is an option when the location is left open.

When updating this skill, prioritize the target's adopted scope and applicable rules for work order, stop and approval conditions, and required verification. Install additional skills or change model settings only when separately requested. Limit existing document edits and cleanup of historical records to the requested scope and preserve meaningful verification evidence.
