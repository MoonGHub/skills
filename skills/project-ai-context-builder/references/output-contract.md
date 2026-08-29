# Portable Output Contract

Read this reference before creating, updating, merging, or retiring project documentation.

Contents: [minimum](#1-minimum-portable-system), [router](#2-new-session-reading-router), [current state](#3-current-state-document-contract), [AGENTS](#4-agents-contracts), [operation](#5-portable-operation-contract), [handoff](#6-optional-handoff-contract), [ownership](#7-ownership-01--ownership-and-refresh), [updates](#8-single-update-matrix).

## 1. Minimum Portable System

Create only what the project needs:

```text
AGENTS.md
AI_CONTEXT/
├── 00_START_HERE.md
├── 00_HANDOFF.md                 # optional; unfinished work only
├── 00_REFRESH_BASELINE.md         # continued Git maintenance; refresh-policy.md
├── 01_PROJECT/                   # identity, stack, structure; may be combined
├── 02_ARCHITECTURE/              # when architecture knowledge is useful
├── <applicable current sections>/
├── <DEVELOPMENT>/AI_DEV_RULE.md  # single project-local update/maintenance rule
├── <OPERATION>/                  # portable bootstrap and canonical commands
├── <MODULE_DETAIL>/              # only high-value boundaries
└── 99_CHANGELOG/
    ├── AI_CHANGELOG.md
    └── YYYY-MM/YYYY-MM-DD.md
```

Root `AGENTS.md`, START_HERE, project identity/structure, portable operation knowledge, and the changelog entrypoint form the minimum system. Combine small current-state topics when that reduces navigation. Create architecture, API, data, design, native, contract-map, module-detail, and folder guides only when applicable. Preserve a useful existing numbering scheme.

Create one project-local AI development rule containing the compressed update matrix from section 8. Root AGENTS or START_HERE must route modification work to it. Do not duplicate that matrix in other project docs.

## 2. New-Session Reading Router

Keep `00_START_HERE.md` small:

- one-sentence project identity and project/service ownership
- task-type → canonical current-state/operation/contract document table
- applicable root-to-local `AGENTS.md` reading rule
- `확인 필요` links and optional active handoff link
- explicit rule not to load all AI_CONTEXT or changelog history by default
- a maintenance-only link to `00_REFRESH_BASELINE.md` when that optional file exists; never route it for ordinary feature work

Future work should read in this order:

1. root `AGENTS.md` and START_HERE
2. intermediate-to-nearest applicable folder `AGENTS.md`; local rules specialize scope but cannot weaken root non-negotiable or explicit user rules
3. routed current-state docs for the task, plus the project-local AI development rule before modification work
4. contract map for a boundary change, operation docs for execution/new-machine setup, and a relevant daily record only when history is needed
5. evidence only through a specific link

## 3. Current-State Document Contract

Include only useful sections:

- responsibility and owner
- stable source anchors: usually 2-6 repository-relative paths or identifiers
- current flow, contracts, invariants, and dependency direction
- consumers and areas to check together
- link to the canonical operation gate; include a gate directly only when it is unique to this owner
- inference and `확인 필요`

Source anchors make targeted revalidation possible; do not use a last-reviewed date as the only trust signal.

## 4. AGENTS Contracts

Root `AGENTS.md` contains project role, the reading router, repository-wide working rules, prohibitions, related context, and check-together routes. It does not duplicate architecture or stack detail.

Place folder guides and ancestor routes only under `SCOPE-01` and `PLACE-01` in `scope-policy.md`. A local guide contains only the actionable local delta:

```md
# AGENTS.md

## Role
<local responsibility>

## Local Rules
- <rules not already stated by an ancestor>

## Do Not
- <local prohibitions>

## Read / Check Together
- `<canonical context or adjacent path>`
```

Omit empty headings and keep the guide within `SIZE-01` unless unique safety-critical or preserved manual instructions justify more. Do not add guides to transparent directories solely to fill every physical level of the chain. For ancestor-routed boundaries selected by `PLACE-01`, prefer one compact table: `Boundary | Role / local risk | Read / check together | Gate` and do not copy current-state prose.

## 5. Portable Operation Contract

Operation guidance is the new-machine source of truth for:

- confirmed toolchain/runtime/package manager and clean-machine prerequisites
- environment key names and where their values are obtained, never the values; derive them from tracked examples, schemas, manifests, or consuming source rather than ignored local environment files
- repository-relative bootstrap, run, build, test, generation, migration, and deploy commands
- platform, target, external-service, and local-infrastructure prerequisites
- minimum gates by change type and known `확인 필요`

Give canonical commands repository-relative source anchors. Mark whether each command is defined/discovered; do not imply it was executed. Keep completed pass/fail results in daily records and the current unfinished result in handoff. Do not canonize a machine-specific absolute path, temporary port, or uncommitted local state; record a non-portable discovered command as such until a portable alternative is verified.

## 6. Optional Handoff Contract

Create `AI_CONTEXT/00_HANDOFF.md` only when unfinished work must cross a session. Keep it about 10-30 lines:

- goal and scope
- completed state
- next 1-3 actions
- changed/affected areas
- latest pass/fail/skip validation
- blockers and `확인 필요`
- branch/worktree and commit/push status
- related current-state docs

Add the handoff link to START_HERE while active. On completion, move durable current facts to owning docs and the completed result to the daily changelog. Remove a managed handoff and its START_HERE link; preserve a manual/unknown handoff while marking completion or removing it from the default route. State that uncommitted or unpushed files cannot be reconstructed on a new machine from documentation alone.

## 7. OWNERSHIP-01 — Ownership and Refresh

Use `<!-- project-ai-context-builder:managed -->` only on a new, fully generated AI_CONTEXT file; do not add a full-file marker to `AGENTS.md` or an existing file. The marker identifies a generated baseline, not permission to discard later explicit user decisions. Absence of the marker means manual, mixed, or unknown ownership.

For new managed sections inside AGENTS or mixed documents, wrap only generated content with `<!-- project-ai-context-builder:section:<id>:start -->` and `<!-- project-ai-context-builder:section:<id>:end -->`. Never enclose pre-existing user content. On later Refresh, replace only a matched managed section and preserve unmatched headings, comments, and explicit rules.

- Preserve manual/unknown files and user instructions. Merge known standard AGENTS sections without dropping unmatched content; otherwise update only matched managed sections or add links. Even in a marked file, retain explicit decisions or instructions that current source cannot reconstruct.
- Adopt an existing unmarked AI_CONTEXT file as fully managed only on an explicit rewrite request after comparing all unique content and preserving user decisions. Otherwise use section-level management.
- Reuse an existing canonical manual document rather than creating an AI_CONTEXT duplicate.
- If implementation contradicts a user-authored instruction, mark and report the conflict instead of deleting the instruction.
- Before retiring a managed doc, rule out rename, sparse checkout, missing submodule, or excluded source; update routing/maps first and preserve unique decisions in an owning doc or evidence.
- Retirement means removing a doc from default routes and fixing inbound links. Delete it only when it is fully managed, its owner disappeared/moved or all unique content was verified in a canonical merge, and recoverable version history is confirmed. Without recoverable history or clear ownership, keep it marked retired/`확인 필요` until the user authorizes deletion.

## 8. Single Update Matrix

| Change | Update |
| --- | --- |
| Current behavior or contract | owning current-state doc, then daily record |
| Cross-boundary contract | owning doc, one canonical contract map, then daily record |
| Local working rule or ownership | apply `PLACE-01`; update the owning current-state doc if behavior changed; then daily record |
| Repository routing or topology | root AGENTS or START_HERE, structure/owner doc, then daily record |
| Bootstrap/build/test/deploy contract | operation doc, then daily record |
| Completed meaningful unit and its pass/fail/skip | daily record |
| Unfinished work and its latest validation | handoff only; add/remove its START_HERE route with lifecycle |
| Removed/moved module | structure/router/maps/AGENTS, retire verified managed docs, then daily record |
| Source anchor or owner path change | owning doc/router/map; daily record when meaningful |
| Verified documentation scope in VCS | seed or advance only its `REFRESH-04` owner rows after docs/anchors/coverage validation; never include a relevant working-tree overlay |
