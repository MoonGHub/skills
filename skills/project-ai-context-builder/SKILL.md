---
name: project-ai-context-builder
description: "Create or maintain portable project-local AI development context: root and folder AGENTS.md, routed AI_CONTEXT current-state and operation docs, contract maps, handoff state, and concise history. Use when the user invokes @project-ai-context-builder or $project-ai-context-builder, or asks to initialize, incrementally refresh, or fully reapply AI development documentation for repository onboarding or cross-session/new-machine continuation. Do not activate for ordinary code changes, generic repository explanations, or general documentation edits that do not request portable AI development context. Supports common and mixed stacks, including Rust, through fact-based specialist routing and fallback."
---

# Project AI Context Builder

## Objective

Build portable project memory that lets a new AI session or machine orient, select only task-relevant context, and continue safely without a default full-repository analysis. Produce documentation only unless the user explicitly requests application changes.

## Information Roles

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
- Respect active VCS ignore rules. Do not traverse, count, open, or use ignored paths as source anchors, AGENTS candidates, or Refresh inputs; derive any relevant generated/runtime boundary only from tracked manifests, inputs, and configuration.
- Do not delete source/runtime/user-owned files. Retire a skill-managed doc only after verifying removal/move or a complete canonical merge, updating inbound links, and preserving unique decisions as required by `references/output-contract.md`.

## Select the Mode

- **Initialize**: meaningful AI context does not exist. Inventory every repository-owned source root and semantic descendant, then create the smallest complete routed documentation system under the current policies.
- **Refresh**: context exists. Start with `references/refresh-policy.md`, use trusted provenance and changed structure to read only affected documentation and source, and automatically extend AGENTS coverage for new, moved, or growing boundaries. A user-named module is a Refresh routing hint, not another mode.
- **Full Reapply** (`전체 다시 적용`): the user explicitly requests repository-wide reapplication, or existing routing is too unreliable to scope safely. Re-inventory all owned source roots, re-evaluate all managed coverage under current policies, and preserve useful manual and existing modular documents.

Initialize and Full Reapply use complete recursive semantic coverage. Refresh applies the same depth and placement rules inside every routed structural candidate, but does not scan or read unrelated owners when trusted provenance can exclude them. New depth or file growth after Initialize is handled by Refresh and is not by itself a Full Reapply trigger.

For a minimal invocation, choose Initialize when meaningful context is absent and Refresh otherwise. Choose Full Reapply only for the conditions above. Ask no setup question unless the repository cannot be inspected or a user choice would materially change scope.

## Progressive Reading

1. Orient with the root `AGENTS.md`, existing `AI_CONTEXT/00_START_HERE.md`, a shallow tree, and manifests. Do not load all `AI_CONTEXT` or all changelogs. In Refresh, next read `references/refresh-policy.md` and the optional `AI_CONTEXT/00_REFRESH_BASELINE.md`; keep the baseline out of ordinary task context.
2. For an existing project, read the applicable `AGENTS.md` chain from root through intermediate folders to the closest `AGENTS.md`; nearer instructions specialize scope but cannot weaken root non-negotiable or explicit user rules.
3. Read only current-state docs routed by `00_START_HERE.md`, the applicable AGENTS chain, or discovered direct dependencies.
4. Load references conditionally:

| Condition | Read |
| --- | --- |
| Initialize or Full Reapply | `references/output-contract.md`, `references/scope-policy.md` |
| Refresh routing and provenance | `references/refresh-policy.md` first; load other references only as it directs |
| Documentation creation, update, merge, or retirement | `references/output-contract.md` |
| Coverage, placement, splitting, or safe discovery decision | `references/scope-policy.md` |
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

1. Snapshot version-control status, then inspect VCS-ignore-aware repository signals. Initialize and Full Reapply recursively enumerate every owned source root to semantic leaf depth. Refresh follows `REFRESH-01` through `REFRESH-04` and enumerates only routed structural candidates unless expansion is required.
2. Detect language, project owners, stack, documentation ownership, semantic boundaries, and source anchors. Apply `SCOPE-01`, `PLACE-01`, and `DISCOVERY-01`; do not infer coverage from an ancestor guide or shallow tree.
3. In Refresh, treat added or deeper folders, renamed paths, and eligible-file-count changes as placement candidates. Evaluate their nearest owning ancestor and descendants so qualifying folder `AGENTS.md` files appear automatically without Full Reapply.
4. Load only the conditional references required by the selected mode and discovered candidates. Give every fact one canonical owner and preserve useful routed files even when the documentation set is large.
5. Update current-state docs before history. Keep START_HERE a task router, folder AGENTS local deltas, operations portable, and contract maps limited to confirmed cross-boundary dependencies.
6. Preserve manual/mixed content and retire only verified obsolete managed documentation under `OWNERSHIP-01`. Put unfinished continuation state in handoff; record meaningful completed changes in the current daily file.
7. In Git repositories, seed or advance only verified Refresh-baseline owner rows under `REFRESH-04`.
8. Run `quality-check.md`, inspect changed Markdown for sensitive-value patterns without reporting values, and re-read the resulting root router, START_HERE, affected AGENTS chains, and changed docs before reporting.

## Output Baseline

Create the minimum structure defined in `references/output-contract.md`:

- root `AGENTS.md` and `AI_CONTEXT/00_START_HERE.md`
- compact project identity, stack, structure, and portable operation knowledge, combining small documents when one owner and audience make that clearer
- only applicable architecture/domain/feature/API/data/design/native/module-detail docs
- folder `AGENTS.md` and compact ancestor routes according to `PLACE-01`, including its narrow high-risk exception
- optional contract maps and `00_HANDOFF.md` only when triggered
- Git projects intended for continued maintenance: `00_REFRESH_BASELINE.md` seeded under `REFRESH-02`; omit it only for non-Git or explicitly one-off documentation
- small `99_CHANGELOG/AI_CHANGELOG.md` index and one `YYYY-MM/YYYY-MM-DD.md` file per day with meaningful completed changes

Do not create placeholder documents for absent concerns. Preserve an existing useful numbering scheme; otherwise choose sections from the specialist reference.

## Final Report

Report concisely in the detected language:

1. mode and analyzed scope
2. created, updated, retired, and preserved manual docs; summarize recursive boundary coverage and every intentional ancestor-routed omission
3. confirmed stack, ownership, flows, contracts, and portable commands
4. inference and `확인 필요`
5. quality and validation results, including skipped code tests because documentation alone changed
6. next recommended area only when it adds value
