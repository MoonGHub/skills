# Incremental Refresh Policy

Read this reference first and only in Refresh mode. It owns baseline trust, change routing, selective reference loading, and Refresh expansion rules.

## REFRESH-01 — Start with Routed Context

Begin with root `AGENTS.md`, `AI_CONTEXT/00_START_HERE.md`, the applicable AGENTS chain, manifests needed to identify owners, and optional `AI_CONTEXT/00_REFRESH_BASELINE.md`. Do not load all AI_CONTEXT, all folder guides, all changelog history, every specialist reference, or every source file.

Use changed paths to choose what to inspect; use source anchors to verify claims. Context efficiency in Refresh means selective reading, not deleting useful documents, reducing semantic coverage, or accepting shallow AGENTS routing.

Load additional references only after routing:

- `output-contract.md` when documentation will be created, updated, merged, or retired
- `scope-policy.md` when a path was added, moved, removed, grew across the placement threshold, exposes a coverage gap, or otherwise needs a coverage/placement decision
- only the specialist reference for an affected owner whose stack-specific contract must be checked
- contract-map, multi-project, changelog, or fallback policy only when its trigger is present
- `quality-check.md` for the final review

If no meaningful documentation candidate remains after routing and anchor checks, do not load output/changelog detail or create a no-op daily record.

## REFRESH-02 — Baseline Trust and Candidates

For a Git repository intended for continued AI-led development, create `AI_CONTEXT/00_REFRESH_BASELINE.md` after verified Initialize or Full Reapply. Omit it only for non-Git or explicitly one-off documentation. Keep it outside ordinary task reading. Include one repository-routing row plus one compact row per stable documentation owner:

```md
<!-- project-ai-context-builder:managed -->
# Refresh Baseline

> Refresh-only routing metadata. Source and current-state documents remain authoritative.

| Scope | Owner paths | Current-state docs | Verified revision | Coverage policy |
| --- | --- | --- | --- | --- |
| `repository-routing` | `.` (topology only) | `AI_CONTEXT/00_START_HERE.md`, `<structure doc>` | `<exact commit id>` | `PLACE-01/v2` |
| `backend/auth` | `backend/src/auth/`, `backend/migrations/` | `AI_CONTEXT/04_API/AUTH.md` | `<exact commit id>` | `PLACE-01/v2` |
```

- `Verified revision` means the row's current claims, representative anchors, routes, direct contracts, and semantic AGENTS coverage were checked against the committed tree at that exact revision.
- `Coverage policy` records the placement policy used for that coverage result. A missing or older value does not prove current coverage.
- The repository-routing row owns only repository-wide path routing, source-root/workspace topology, and route documents; it does not absorb child architecture or contract ownership. Use its revision for a repository-wide name/status diff so a new top-level project or source root cannot fall outside existing owner paths.
- Trust a row only when its revision resolves and is an ancestor of current `HEAD`, owner paths still cover current topology, the coverage policy is current, and no workspace manifest, source-root, router, or owner change invalidates it.
- Dates, branch names, clean status, file existence, and document mtimes are not freshness evidence.

Refresh candidates are the union of:

- repository-wide path-name changes from the trusted repository-routing revision
- `Verified revision..HEAD` paths for each routed owner and linked current-state documents
- pre-write dirty and non-ignored untracked paths
- added, deleted, moved, or renamed paths and their nearest meaningful owning ancestors
- changed manifests, source roots, routes, interfaces, generators, or ownership declarations
- direct producers and consumers of a changed contract

Apply `DISCOVERY-01` before classification. Changed paths route inspection; they never prove a current-state claim by themselves.

## REFRESH-03 — Structural Growth and Expansion

For a trusted owner with no path/topology change, inspect only changed contracts, routed documents, representative anchors, and confirmed direct consumers.

When files or folders were added, moved, removed, or renamed, recursively enumerate the nearest owning ancestor and every changed/new descendant to semantic leaf depth. Recompute directly owned eligible-file counts and apply `SCOPE-01` and `PLACE-01`. This must automatically create or update a deeper `AGENTS.md` when a new meaningful boundary qualifies, including when an existing zero-to-two-file boundary grows to three or more eligible files. It must also update the nearest ancestor route when the boundary remains small. Ordinary structural growth after Initialize never requires Full Reapply.

If a row is absent, incomplete, divergent, or untrusted, perform a structural coverage audit for the affected owner or owners, then deep-read only the anchors and contracts needed to restore trust. Escalate only under the Full Reapply mode-selection conditions in `SKILL.md`. A single new folder, deeper subtree, placement transition, or localized gap is not a Full Reapply trigger.

## REFRESH-04 — Advance Provenance

- Advance only rows whose linked documents, representative anchors, direct contracts, and AGENTS coverage were verified.
- Leave untouched owners at their prior revision.
- A committed revision never covers relevant uncommitted or untracked work; record unfinished continuation state in handoff and re-evaluate when reproducible.
- Initialize and Full Reapply may seed verified rows after complete documentation review.
- Do not store absolute machine paths, credential-bearing remotes, raw diffs/logs, or private values.
