# Selecting and customizing workflow documents

Templates are Markdown source documents. Merge selected content into the target, resolve every placeholder to a concrete value or explicit reason for absence, and remove unused sections and links. Preserve existing instructions, specifications, tasks and meaningful evidence.

| Template | Target role |
| --- | --- |
| [AGENTS.md](../templates/AGENTS.md) | Persistent working contract, scope and actual command/document pointers |
| [README.md](../templates/README.md) | Current project state, purpose, setup, development commands and navigation |
| [Architecture](../templates/docs/architecture.md) | Optional current boundaries/data flow when README is insufficient; link ADRs for significant decision history when needed |

Start with existing AGENTS.md and README content. Keep simple architecture and tooling decisions in README; separate documents are optional. Link an existing tooling document rather than requiring one. Remove unsupported command rows and describe absent checks honestly. Node-specific template fields apply only when the target uses Node.

Preserve the target's task tracker and completed evidence. If it uses phased Markdown tasks, link its queue and keep task/phase/index statuses consistent. If no work is planned, explicitly state that tracking has not been created; do not create empty phases just to adopt instructions. Concrete requirements, phase decomposition and task generation belong to a separate planning request.

Keep working rules, including [document responsibilities](workflow.md#documentation-management), in the target AGENTS.md and refer to it from other documents when present. Specifications own requirements and acceptance; tasks own execution plans and observed results; existing task management documents own current progress and next actions. README remains a current-state entry point. Keep guidance coherent without dated update sections or editing diaries. Preserve meaningful task dates and evidence in their owning documents. Link results instead of duplicating them.
