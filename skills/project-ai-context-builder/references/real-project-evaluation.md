# Real-Project Behavioral Evaluation

Read this only when maintaining, releasing, or behaviorally evaluating this skill. Evaluate with real repositories and agent judgment; do not add an evaluator script to the skill.

## Corpus and Isolation

- For a core workflow change, use at least three real repositories covering a single-project shape, a multi-project or mixed shape, and Rust or an unmatched stack. Include both existing AI context and a repository evaluated as Initialize.
- Run every affected mode at least twice across distinct repositories or revisions. For a change shared by all modes, run Initialize, Refresh, and Deepen at least twice each.
- Prefer fresh sessions or isolated agents when available. Give only the skill, task, repository, and requested scope; do not reveal expected output, prior diagnoses, or another run's artifacts.
- Work from disposable copies or isolated worktrees. Never remove live documentation, rewrite user branches, expose secrets, or run production/deployment actions for evaluation.
- Use a repository's real source and commit history. Toy fixtures and invented file trees may supplement edge cases but cannot satisfy the release gate.

## Mode Trials

### Initialize

1. Use a source-complete isolated copy where generated AI context is absent from the evaluator's view; preserve ordinary project documentation as possible canonical input.
2. Run at least twice. When fresh sessions or isolated agents are available, repeat one repository at the same revision without sharing the first output; otherwise use distinct real repositories or revisions and disclose that independent consistency was not tested.
3. Compare semantic ownership, the meaningful-boundary inventory, root-to-nearest AGENTS coverage, source anchors, applicable documents, and `확인 필요`; byte-identical prose is not required.
4. Fail if the run invents behavior, creates absent-topic placeholders, duplicates manual docs, mirrors the physical tree with folder guides, expands a new folder guide past its soft budget without unique justification, or leaves an independent owner/high-risk boundary behind a generic route that requires broad rediscovery.

### Refresh

1. Start from real existing context and an earlier verified commit. Use at least one localized commit range and one contract, topology, or owner-boundary range.
2. On each run, record the baseline revision, current revision, owner paths, committed diff paths, and pre-write dirty/untracked paths. Do not paste raw source or sensitive values into evaluation notes.
3. Confirm that the run checks manifests/routes, compares already routed owners and changed topology with semantic AGENTS coverage, locally deepens only each confirmed uncovered boundary, maps changed producers to direct consumers, preserves unrelated/manual content, and advances only verified baseline rows.
4. Include unchanged-scope and single-coverage-gap controls where an ancestor AGENTS exists but does not make one routed meaningful boundary actionable. Fail if ancestor-file presence is accepted as coverage, a clean worktree is treated as proof of freshness, a relevant overlay is covered by `HEAD`, a changed contract is missed, an already routed meaningful owner remains unreachable without broad rediscovery, one local gap expands into project-wide Deepen or unrelated sibling rewrites, or unrelated documentation is otherwise rewritten.

### Deepen

1. Across the trials, choose one real container-like area with multiple meaningful or transparent descendants and one bounded leaf module. Before writing, identify the requested-area boundary, in-scope descendant candidates, applicable AGENTS chain, owning current-state docs, source anchors, and direct consumers.
2. Run twice on different modules or repositories without loading unrelated AI context. Confirm that each included descendant receives a nearest local delta or an explicit actionable ancestor route, and that transparent containers or ordinary leaves are skipped with a reason.
3. Fail if analysis treats the target container as the only candidate despite distinct descendants, accepts generic ancestor-file presence as coverage, silently expands outside the requested area or into a full audit, leaves an included boundary without its role/risks/gates route, turns a folder guide into module-detail prose, copies schema/detail into multiple owners, misses a direct consumer, or rewrites an unrelated sibling.

## Evidence and Scoring

Keep raw artifacts outside the installed skill and its release tree. For each run retain only as long as needed:

- task prompt, repository identity without credentials, exact revision, initial status, mode, and requested scope
- files read and changed, source anchors supporting key claims, baseline rows used or rejected, and concise diff summary
- quality ratings from `quality-check.md`, failures, corrective change, and rerun result

Score these gates `pass`, `fail`, or `not applicable`: mode/scope, factual grounding, routing/context economy, boundary coverage, manual and dirty-worktree preservation, portable continuation, history ownership, and Refresh provenance. A run fails overall on any fabricated fact, missed changed contract or direct consumer, unauthorized manual-content loss, sensitive-value disclosure, unjustified full scan, or false baseline advancement.

When two runs expose the same failure class, treat it as a skill-policy defect, revise the owning rule once, and rerun the affected mode on both a previously failing case and a different repository. Report the corpus, revisions, run counts, failures, and rerun outcomes concisely; do not claim independent-session validation when it was not performed.
