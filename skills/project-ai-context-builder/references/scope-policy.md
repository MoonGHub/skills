# Scope and Size Policy

Use this reference only when choosing documentation coverage, depth, or splitting.

## Inclusion Test

Document a work area when at least one is true:

- future work will likely modify it or inspect it for impact
- it owns a stable module, feature, domain, interface, data boundary, or operational responsibility
- changing it can affect API/IPC, routing, auth, state, persistence, native behavior, design, build, deployment, or an external integration
- it has non-obvious local rules that a parent document cannot express concisely

## Semantic AGENTS Depth

For each included work area, identify the nearest meaningful boundary. Create a folder `AGENTS.md` when an ancestor cannot concisely make work at that boundary actionable through at least one of these deltas:

- an independent project, app, package, crate, module, feature, or domain responsibility
- a distinct build/runtime/test lifecycle or generated, native, security, auth, persistence, migration, or external-integration boundary
- boundary-specific prohibitions, validation gates, change-impact checks, or paths that must be read or changed together

A unique role, ownership boundary, risk, or check-together route counts as local delta; a folder does not need a different coding style to qualify. Keep architecture, current behavior, schemas, and app-wide file inventories in their canonical current-state or module-detail docs, and link them from AGENTS instead of copying them.

Do not mirror the physical directory tree. Skip transparent grouping directories and ordinary leaves, and place the guide at the nearest boundary that changes how work is understood, routed, modified, or validated. An ancestor may cover a small child boundary only when it names that boundary and supplies an actionable route without broad repository rediscovery.

The chain is deep enough when a task can follow root instructions through the nearest applicable semantic boundary to the owning current-state docs, adjacent contracts, and validation gate. Physical directories between those guides do not each need an `AGENTS.md`.

- **Initialize**: inventory meaningful boundaries before writing and verify that each is covered by a nearest guide or an explicit actionable ancestor route.
- **Refresh**: build a bounded coverage candidate set from START_HERE project owners and task-router rows, structure docs, trusted baseline owner paths, workspace members or manifests, and changed topology. For each candidate, test whether the existing AGENTS chain names or directly routes its local role, non-obvious rules or risks, adjacent contracts/check-together paths, and validation gate; the mere presence of an ancestor `AGENTS.md` is not coverage. Deepen only each confirmed gap's nearest AGENTS delta and routes, even when no source change exists. Leave unrelated siblings untouched and do not expand one gap into project-wide Deepen; repeated gaps across independent owners may trigger a full audit.
- **Deepen**: stay inside the requested area and build a bounded candidate set from its entrypoints, manifests or workspace members, routes/interfaces, state/data/persistence, tests, direct contracts, and semantic source subtrees. Apply the Inclusion Test to the target and its meaningful descendants; do not treat the target container as the only candidate when distinct descendant responsibilities exist. For each included boundary, ensure a nearest AGENTS delta or an explicit actionable ancestor route even when no source change exists. Ancestor-file presence alone is not coverage. Skip a physical `src`/grouping directory when it is transparent, but continue through it to evaluate meaningful descendants; stop at ordinary leaves and never expand to unrelated siblings or outside the requested area.

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

Treat a folder guide above its soft limit as a compaction review trigger, not deletion authority. For new or fully managed content, move architecture/current-state prose, examples, and repeated parent rules to their canonical owners and keep links plus actionable local delta. Preserve manual or unknown-ownership instructions under `output-contract.md`; if their unique content prevents safe compaction, retain it and report the reason.

## Deduplication and Splitting

- Give each fact one canonical current-state owner and link to it elsewhere.
- Do not repeat root rules in folder `AGENTS.md`, current state in changelogs, or full schemas in contract maps.
- Combine overview, stack, or structure for a small project when one concise document is easier to route.
- Split only when one file mixes independent owners, audiences, or contracts, or requires scanning unrelated material for a common task.
- Do not create a document merely to state that a concern is absent. Put an important absence in START_HERE, overview, or the owning architecture doc in one line.
- Before adding a file, identify its unique reader, owner, and maintenance trigger. Merge or omit it when these are not distinct.
