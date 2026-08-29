# Scope and Size Policy

Use this reference only when choosing documentation coverage, depth, or splitting.

## Inclusion Test

Document a work area when at least one is true:

- future work will likely modify it or inspect it for impact
- it owns a stable module, feature, domain, interface, data boundary, or operational responsibility
- changing it can affect API/IPC, routing, auth, state, persistence, native behavior, design, build, deployment, or an external integration
- it has non-obvious local rules that a parent document cannot express concisely

## Semantic AGENTS Depth

Apply one recursive depth standard in Initialize, Refresh, and Deepen. Starting from each source root in the mode's scope, traverse candidate descendants until excluded output or ordinary leaves; do not stop at the repository top level, `src`, a language package root, or the first child layer while deeper candidate boundaries remain. Use the detected specialist reference for concrete backend, frontend, mobile, Rust, or fallback candidates.

Mode changes breadth and reading cost, not the depth or placement test:

- **Initialize**: recursively inventory every repository-owned source root and workspace member before writing.
- **Refresh**: recursively inventory all repository-owned source roots at the structural level (paths, manifests, entrypoints, file ownership, and counts), then open source content and update docs only for routed, changed, stale, new, or uncovered boundaries. This coverage pass is not permission for an unrelated full content audit.
- **Deepen**: recursively inventory the requested target and all candidate descendants, then inspect only their direct contracts and confirmed consumers. Never expand to unrelated siblings or outside the requested area.

For each candidate, apply the Inclusion Test and identify the nearest meaningful boundary. A meaningful boundary has at least one of these deltas:

- an independent project, app, package, crate, module, feature, or domain responsibility
- a distinct build/runtime/test lifecycle or generated, native, security, auth, persistence, migration, or external-integration boundary
- boundary-specific prohibitions, validation gates, change-impact checks, or paths that must be read or changed together

A unique role, ownership boundary, risk, or check-together route counts as local delta; a folder does not need a different coding style to qualify. Keep architecture, current behavior, schemas, and app-wide file inventories in their canonical current-state or module-detail docs, and link them from AGENTS instead of copying them.

## File-Count Placement Rule

Count **directly owned eligible files** after separating distinct descendant candidates. Eligible files are non-ignored, repository-owned source, configuration, interface, test, migration, or content files that implement or govern the boundary. Do not count skill-managed `AGENTS.md`/`AI_CONTEXT`, files owned by a child boundary, VCS-ignored paths, or generated, vendor, dependency, build, cache, coverage, and static binary output.

Apply this deterministic placement rule to every included meaningful boundary:

- **Three or more eligible files**: create or update that boundary's own `AGENTS.md`. A generic ancestor route is not a substitute.
- **Zero, one, or two eligible files**: do not create a local `AGENTS.md`. Route the boundary only from the nearest meaningful ancestor guide, naming its path and role plus any local prohibition or risk, canonical context/check-together path, and validation gate.
- Continue evaluating descendants even when the current folder has zero to two directly owned files or is a transparent `src`/grouping container.

If a zero-to-two-file boundary already has a skill-managed local guide, preserve its unique rules in the nearest ancestor and retire it only under `output-contract.md`. Preserve manual or unknown-ownership guides; report that they remain instead of deleting them.

Do not mirror the physical directory tree. Skip non-meaningful grouping directories and ordinary leaves. The zero-to-two-file exception is the only size-based ancestor substitution for an included boundary; simple ancestor-file presence never counts as coverage.

The chain is deep enough when a task can follow root instructions through the nearest applicable semantic boundary to the owning current-state docs, adjacent contracts, and validation gate. Physical directories between those guides do not each need an `AGENTS.md`.

## Exclusions

Exclude dependencies, generated output, vendor code, caches, build artifacts, coverage, empty folders, ordinary leaf components, trivial helpers, static assets, and file-by-file generated-model inventories. Common examples include `node_modules`, `.next`, `dist`, `build`, `target`, `.gradle`, `coverage`, `Pods`, `.cxx`, and `vendor`.

Document an excluded area only when its ownership or generation boundary affects source work. Record the source input, regeneration command when confirmed, consumers, and hand-edit restriction—not generated internals.

### VCS-Ignored Paths

Apply active VCS ignore rules before any recursive inventory, file count, content read, source-anchor selection, or change classification. In Git repositories, prefer `git ls-files --cached --others --exclude-standard` or an ignore-aware `rg --files`; this covers repository and nested `.gitignore`, `.git/info/exclude`, and configured global excludes. Do not use `git status --ignored`, `git ls-files --ignored`, `rg --no-ignore`, or an unfiltered recursive `find` for repository discovery.

- Ignored paths never enter semantic candidates, eligible-file counts, source anchors, dirty/untracked Refresh inputs, contract maps, or evidence.
- Do not open an ignored path merely because its name suggests source, configuration, credentials, or useful runtime state.
- When ignored generated, dependency, cache, runtime, or local-configuration output affects source work, inspect only tracked manifests, generator inputs, example/schema files, and consuming source. Document the boundary and regeneration/ownership rule without reading the ignored contents.
- For a non-Git repository, apply the equivalent ignore mechanism of its detected VCS. If no VCS exists, use the explicit exclusions above and project-local ignore files when supported by the discovery tool.

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
