---
name: project-ai-context-builder
description: "Analyze an existing or newly initialized software repository and create, refresh, or deepen portable AI-led development documentation: root and folder AGENTS.md, an adaptive AI_CONTEXT knowledge base, contract maps, handoff state, and concise changelogs. Use when the user invokes @project-ai-context-builder or $project-ai-context-builder, after /init, while onboarding Codex, when project context is stale, or when a new session or machine must continue work without re-analyzing the whole repository. Supports Java/Spring Boot, React/Vite/Next.js, React Native, Rust/Cargo workspaces, applications and libraries, content/static sites, mixed repositories, and unfamiliar stacks through a fact-based fallback."
---

# Project AI Context Builder

## Objective

Build portable project memory that lets a new AI session or machine orient, select only task-relevant context, and continue safely without a default full-repository analysis. Produce documentation only unless the user explicitly requests application changes.

## Canonical Information Roles

Keep each fact in one authoritative place and link to it elsewhere:

- Source, configuration, manifests, and migrations are implementation truth.
- Subject-specific `AI_CONTEXT` docs are the compressed current state and current contracts.
- Root and folder `AGENTS.md` contain working instructions, prohibitions, and reading routes, not duplicated architecture prose.
- Contract maps contain cross-boundary ownership, consumers, invariants, and change impact.
- Operation docs contain portable bootstrap prerequisites, canonical commands, and minimum gates.
- Daily changelogs contain completed changes and the validation result at that time; they do not reconstruct current state.
- Optional `AI_CONTEXT/00_HANDOFF.md` contains only unfinished work state.
- Evidence contains linked diagnostic or audit detail only.

When docs and implementation conflict, verify the relevant source anchors, correct the owning current-state doc, and record the correction in the current daily changelog.

## Guardrails

- Modify only `AGENTS.md`, `AI_CONTEXT/**`, and related Markdown guidance unless the user explicitly broadens scope.
- Distinguish observed facts, reasoned inference, and an explicit unresolved label (`확인 필요` or its detected-language equivalent); never present inference as confirmed behavior.
- Never record secret or credential values, private keys, auth codes, signing material, unnecessary personal data, or production-only access data. Record safe key names and purpose only.
- Preserve identifiers and commands exactly as found. Do not invent product intent, runtime policy, or framework rules.
- Preserve user-authored and unknown-ownership documentation. Never silently replace a user instruction because code appears inconsistent.
- Snapshot version-control status before writing when available. Preserve unrelated user changes, never revert them, and distinguish the agent-introduced documentation delta during validation.
- Use repository-relative paths and portable commands. Preserve a discovered machine-specific command as an observed non-portable fact/`확인 필요`; promote only a verified portable form to the canonical operation command.
- Do not treat dependency, generated, vendor, build, cache, or coverage output as owned source.
- Do not delete source/runtime/user-owned files. Retire a skill-managed doc only after verifying removal/move or a complete canonical merge, updating inbound links, and preserving unique decisions as required by `references/output-contract.md`.

## Select the Mode

- **Initialize**: meaningful AI context does not exist. Map the semantic work-area boundaries defined by `references/scope-policy.md` and create the smallest complete documentation system that reaches them.
- **Refresh**: context exists. Verify topology, routing, source anchors, available changed paths, and AGENTS coverage for already routed owners first; update stale, affected, or structurally uncovered areas incrementally. Do not count an ancestor `AGENTS.md` as coverage unless it makes the routed meaningful boundary actionable. Deepen only each confirmed coverage gap's local delta and routes; do not broaden the run into project-wide Deepen.
- **Deepen**: the user names a module or area. Analyze its nearest semantic boundary and direct contracts, then update only its routed documentation and applicable AGENTS chain.

Perform a full audit only for Initialize, an explicit full-audit request, a major workspace/topology change, many missing source anchors, repeated AGENTS coverage gaps across independent owners, or documentation that is too unreliable to route work safely. Ask no setup questions for a minimal invocation unless the repository cannot be inspected or a user choice would materially change scope.

## Progressive Reading

1. Orient with the root `AGENTS.md`, existing `AI_CONTEXT/00_START_HERE.md`, a shallow tree, and manifests. Do not load all `AI_CONTEXT` or all changelogs. During Refresh only, also load the optional `AI_CONTEXT/00_REFRESH_BASELINE.md`; keep it out of ordinary task context.
2. For an existing project, read the applicable `AGENTS.md` chain from root through intermediate folders to the closest `AGENTS.md`; nearer instructions specialize scope but cannot weaken root non-negotiable or explicit user rules.
3. Read only current-state docs routed by `00_START_HERE.md`, the applicable AGENTS chain, or discovered direct dependencies.
4. Load references conditionally:

| Condition | Read |
| --- | --- |
| Any documentation creation, update, merge, or retirement | `references/output-contract.md` |
| Initialize or structural output redesign | `references/scope-policy.md` |
| Coverage/splitting decision during Refresh or Deepen | `references/scope-policy.md` |
| Cross-boundary dependency confirmed | `references/contract-map-policy.md` |
| Changelog creation, update, or migration | `references/changelog-policy.md` |
| Multiple app/service/package/crate candidates are detected | `references/multi-project-patterns.md` |
| A detected project/stack has no specialist match | `references/fallback-strategy.md` |
| Final review | `references/quality-check.md` |
| User asks how to invoke the skill | `references/prompt-patterns.md` |
| Maintaining, releasing, or behaviorally evaluating this skill | `references/real-project-evaluation.md` |

Read only the detected specialist reference, or the minimum set needed for a genuinely mixed project:

| Signals | Specialist reference |
| --- | --- |
| Spring Boot dependency or annotation plus Gradle/Maven Java source | `references/spring-boot-analysis.md` |
| React Native dependency/Metro plus native roots | `references/react-native-analysis.md` |
| React, Vite, or Next.js without the React Native signals above | `references/frontend-react-analysis.md` |
| Cargo workspace/crate, `Cargo.toml`, `src/main.rs` or `src/lib.rs` | `references/rust-analysis.md` |

Evaluate specialist routing per independent project. In mixed repositories, use fallback for each unmatched project even when another project has a specialist match.

## Workflow

1. Inspect read-only repository signals with fast search: manifests, source roots, entrypoints, routes or interfaces, state/data/persistence, configuration, build/test/run commands, tests, integrations, and existing docs. Respect exclusions.
2. Detect documentation language, mode, project shape, project ownership boundaries, semantic AGENTS boundaries, and current documentation ownership. Prefer the user's language when signals conflict.
3. Build a small source-anchor map for each affected work area. In Refresh, use the per-scope ledger from `00_REFRESH_BASELINE.md` only when its repository-relative owner paths still cover current topology and its exact VCS revisions resolve as ancestors of the current revision. Diff each trusted row through current `HEAD`, add pre-write dirty and untracked paths, and map changed producers to owning docs and direct consumers. A row proves only the committed range already verified; it never proves a claim by itself or covers a relevant working-tree overlay. For missing or untrusted rows, compare core claims with representative anchors for every routed owner and expand from any mismatch. Advance only verified rows after documentation review, as defined in `references/output-contract.md`.
4. Read the conditional references above and plan the minimum files that give each fact one owner. For every meaningful boundary in scope, use `references/scope-policy.md` to choose a nearest folder AGENTS delta or an explicit actionable ancestor route. During Refresh, run the bounded AGENTS coverage pass defined there before finalizing this file plan.
5. Create or update current-state docs before history. Make `00_START_HERE.md` a task router, make folder `AGENTS.md` local deltas, and keep source anchors near the contracts they support. Put the compressed update matrix from `references/output-contract.md` in exactly one project-local AI development rule, then route modification work to it from root AGENTS or START_HERE so continuity does not depend on this installed skill.
6. Update operation guidance when bootstrap, toolchain, environment-key names, build/test/deploy commands, platform prerequisites, or minimum gates changed.
7. Create or update one canonical contract map only for a confirmed cross-boundary dependency.
8. If unfinished work must survive a session, write the optional handoff. Do not put unfinished work in the completed-change log.
9. Preserve manual/mixed docs and retire only verified obsolete skill-managed docs according to `references/output-contract.md`.
10. Update the current daily changelog after the owning current-state docs. Use same-month evidence only when durable detail is necessary.
11. Review routed links, source anchors, semantic AGENTS depth, ownership, portability, concise size, and documentation-only scope with `references/quality-check.md`. Search changed Markdown for generic and project-specific sensitive-value patterns, inspect matches without echoing values in the report, and separate pre-existing worktree changes from the agent delta.
12. Re-read the generated root router, START_HERE, affected AGENTS chain, representative meaningful-boundary paths, and changed docs; fix routing gaps before reporting.

## Output Baseline

Create the minimum structure defined in `references/output-contract.md`:

- root `AGENTS.md` and `AI_CONTEXT/00_START_HERE.md`
- compact project identity, stack, structure, and portable operation knowledge, combining small documents when one owner and audience make that clearer
- only applicable architecture/domain/feature/API/data/design/native/module-detail docs
- folder `AGENTS.md` at the nearest meaningful module/ownership/risk boundary when an ancestor cannot provide its actionable local role, rules, prohibitions, and check-together route; skip transparent directories and ordinary leaves
- optional contract maps and `00_HANDOFF.md` only when triggered
- optional `00_REFRESH_BASELINE.md` as Refresh-only VCS provenance when repeated incremental maintenance benefits
- small `99_CHANGELOG/AI_CHANGELOG.md` index and one `YYYY-MM/YYYY-MM-DD.md` file per day with meaningful completed changes

Do not create placeholder documents for absent concerns. Preserve an existing useful numbering scheme; otherwise choose sections from the specialist reference.

## Final Report

Report concisely in the detected language:

1. mode and analyzed scope
2. created, updated, retired, and preserved manual docs
3. confirmed stack, ownership, flows, contracts, and portable commands
4. inference and `확인 필요`
5. quality and validation results, including skipped code tests because documentation alone changed
6. next recommended area only when it adds value
