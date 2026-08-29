# Multi-Project Ownership

Read this reference only when multiple independently owned or operated projects coexist.

## Boundary Test

A workspace package, module, or Cargo crate is not automatically a separate documented project. Give it independent AI_CONTEXT when it has a distinct owner plus its own build, deploy, runtime, release, or operational lifecycle. Otherwise keep one project context and describe the internal module in structure/module detail.

## Documentation Ownership

- Root START_HERE orients across projects and routes task types; it does not copy child architecture.
- Root current-state docs own repository-wide topology, shared tooling, and cross-project contracts only.
- Each independent project owns its stack, internal architecture, operation, folder instructions, and changelog detail.
- Root `AGENTS.md` states shared rules; child/folder AGENTS contain only local delta.
- A canonical manual doc may satisfy a role for multiple projects; link it instead of cloning it.

## Cross-Project Changes

Place a cross-project contract map at the lowest common owner. Record only the edge, owners, consumers, invariant, source anchors, and coordinated checks. Keep each project's internal contract in its own current-state doc.

Record a service-internal change only in that service's daily file. For a true cross-project change, the root daily entry summarizes the repository-level contract and links child records without duplicating their details.

On Refresh, apply `REFRESH-01` through `REFRESH-04` per independent owner. Expand to the whole workspace only when the Full Reapply mode conditions in `SKILL.md` are met; a localized project or folder growth does not justify reading unrelated projects.
