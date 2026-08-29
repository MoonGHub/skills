# Real-Project Behavioral Evaluation

Read this only when maintaining, releasing, or behaviorally evaluating this skill. Evaluate with real repositories and agent judgment; do not add an evaluator script to the skill.

## Corpus and Isolation

- For a core workflow change, use at least three real repositories covering a single-project shape, a multi-project or mixed shape, and Rust or an unmatched stack. Include both existing AI context and a repository evaluated as Initialize.
- Run every affected mode at least twice across distinct repositories or revisions. For a change shared by all modes, run Initialize, Refresh, and Full Reapply at least twice each.
- Across the corpus, include meaningful candidate boundaries with zero, one, two, and at least three directly owned eligible files, a valid narrow `PLACE-01` exception, and a transparent container with deeper meaningful descendants.
- Include repositories with ordinary ignored dependency/build output and ignored local-configuration paths; evaluate from tracked inputs without opening or copying ignored contents.
- Prefer fresh sessions or isolated agents when available. Give only the skill, task, repository, and requested scope; do not reveal expected output, prior diagnoses, or another run's artifacts.
- Work from disposable copies or isolated worktrees. Never remove live documentation, rewrite user branches, expose secrets, or run production/deployment actions for evaluation.
- Use a repository's real source and commit history. Toy fixtures and invented file trees may supplement edge cases but cannot satisfy the release gate.

## Activation and Mode Selection

Test activation separately from output behavior with direct, indirect, incomplete, non-trigger, and safety-edge requests. Include Korean and English phrasing where the skill is expected to support both.

- explicit `$project-ai-context-builder` with no meaningful context → Initialize
- explicit or indirect portable-context maintenance request with existing context → Refresh
- named module or folder with existing context → Refresh with a routing hint, never a separate mode
- explicit `전체 다시 적용`, full reapplication, or equivalent → Full Reapply
- ordinary code changes, generic repository explanations, and general documentation edits without portable AI-context intent → no implicit activation
- uninspectable repository or a missing choice that materially changes scope → one focused question rather than fabricated assumptions

Fail activation when the skill over-triggers on ordinary work, misses a recognizable portable-context goal, selects Full Reapply for routine growth, or emits a removed mode.

## Mode Trials

### Initialize

1. Use a source-complete isolated copy where generated AI context is absent from the evaluator's view; preserve ordinary project documentation as possible canonical input.
2. Run at least twice. When fresh sessions or isolated agents are available, repeat one repository at the same revision without sharing the first output; otherwise use distinct real repositories or revisions and disclose that independent consistency was not tested.
3. Compare semantic ownership, the recursively discovered meaningful-boundary inventory, directly owned eligible-file counts, root-to-nearest AGENTS coverage, source anchors, applicable documents, and `확인 필요`; byte-identical prose is not required.
4. Fail if the run stops at top or first-child depth, invents behavior, creates absent-topic placeholders, duplicates manual docs, mirrors non-meaningful physical directories, violates `PLACE-01`, omits a qualifying boundary, or expands a new guide past `SIZE-01` without unique justification.

### Refresh

1. Start from real existing context and an earlier verified commit. Include trusted and untrusted baseline cases, a localized contract change, and a structural change.
2. Record the baseline/current revisions, owner paths, committed diff paths, pre-write dirty/non-ignored-untracked paths, references loaded, source areas opened, and any rejected row without copying raw source or sensitive values.
3. Confirm `REFRESH-01` through `REFRESH-04`: unaffected trusted owners remain unread, routed claims are anchor-checked, direct consumers are covered, and only verified owner rows advance.
4. Include controls for an unchanged owner, a new nested folder, an existing boundary growing from two to three eligible files, a valid small high-risk boundary, and a move/delete or manifest change. Confirm that Refresh recursively evaluates the affected ancestor and descendants and creates or reroutes AGENTS coverage without Full Reapply.
5. Fail if Refresh performs an unrelated whole-repository read, treats clean status as freshness, misses a changed contract/direct consumer/new semantic boundary, fails a `PLACE-01` transition, loads all AI_CONTEXT/history by default, rewrites unrelated documentation, or advances false provenance.

### Full Reapply

1. Use existing, nontrivial AI context and explicitly request Full Reapply. Inventory every owned source root and project owner under the current policies.
2. Confirm that useful modular files, manual/mixed instructions, unique decisions, and current routing are preserved while stale managed coverage and contracts are corrected.
3. Include a repository with many valid routed documents and verify that the run does not collapse them merely to reduce file count.
4. Fail if the run behaves like a localized Refresh, stops at shallow depth, deletes or overwrites manual content, preserves demonstrably stale managed claims, mirrors ordinary directories, or merges distinct owners without a routing benefit.

## Evidence and Scoring

Keep raw artifacts outside the installed skill and its release tree. For each run retain only as long as needed:

- task prompt, repository identity without credentials, exact revision, initial status, mode, and requested scope
- files read and changed, source anchors supporting key claims, baseline rows used or rejected, and concise diff summary
- quality ratings from `quality-check.md`, activation/mode result, failures, corrective change, and rerun result

Keep one concise versioned evaluation summary outside the installed skill, such as the source repository's `evaluations/project-ai-context-builder/<date-or-version>.md`. Record corpus/revisions, activation cases, mode counts, observable reading scope, failures, and rerun outcomes; do not retain source dumps or private values.

Score these gates `pass`, `fail`, or `not applicable`: activation/mode, factual grounding, Refresh reading economy, routing, boundary coverage, discovery discipline, manual and dirty-worktree preservation, portable continuation, history ownership, and Refresh provenance. A run fails overall on any fabricated fact, missed changed contract/direct consumer/new structural boundary, ignored or external-symlink traversal, unauthorized manual-content loss, sensitive-value disclosure, unjustified full scan, false Full Reapply selection, or false baseline advancement.

When two runs expose the same failure class, treat it as a skill-policy defect, revise the owning rule once, and rerun the affected mode on both a previously failing case and a different repository. Report the corpus, revisions, run counts, failures, and rerun outcomes concisely; do not claim independent-session validation when it was not performed.
