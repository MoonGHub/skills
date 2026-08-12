# Scope and Size Policy

Use this reference only when choosing documentation coverage, depth, or splitting.

## Inclusion Test

Document a work area when at least one is true:

- future work will likely modify it or inspect it for impact
- it owns a stable module, feature, domain, interface, data boundary, or operational responsibility
- changing it can affect API/IPC, routing, auth, state, persistence, native behavior, design, build, deployment, or an external integration
- it has non-obvious local rules that a parent document cannot express concisely

Create folder `AGENTS.md` only when local instructions differ from the parent. Put app-wide entrypoints, shared utilities, generated boundaries, and high-risk integrations in current-state or module-detail docs instead of producing file-level guides.

## Exclusions

Exclude dependencies, generated output, vendor code, caches, build artifacts, coverage, empty folders, ordinary leaf components, trivial helpers, static assets, and file-by-file generated-model inventories. Common examples include `node_modules`, `.next`, `dist`, `build`, `target`, `.gradle`, `coverage`, `Pods`, `.cxx`, and `vendor`.

Document an excluded area only when its ownership or generation boundary affects source work. Record the source input, regeneration command when confirmed, consumers, and hand-edit restriction—not generated internals.

## Context Budget

Prefer the fewest documents that preserve distinct ownership and routing:

- root `AGENTS.md`: about 40-100 lines
- folder `AGENTS.md`: about 15-50 lines of local delta
- `00_START_HERE.md`: about 20-60 lines
- project/current-state docs: about 30-120 lines
- module detail: about 40-160 lines
- contract maps: the smallest useful table or list
- daily changelog entry: about 5-10 lines

These are soft limits. Safety-critical contracts win, but split unrelated owners or audiences rather than expanding a catch-all file.

## Deduplication and Splitting

- Give each fact one canonical current-state owner and link to it elsewhere.
- Do not repeat root rules in folder `AGENTS.md`, current state in changelogs, or full schemas in contract maps.
- Combine overview, stack, or structure for a small project when one concise document is easier to route.
- Split only when one file mixes independent owners, audiences, or contracts, or requires scanning unrelated material for a common task.
- Do not create a document merely to state that a concern is absent. Put an important absence in START_HERE, overview, or the owning architecture doc in one line.
- Before adding a file, identify its unique reader, owner, and maintenance trigger. Merge or omit it when these are not distinct.
