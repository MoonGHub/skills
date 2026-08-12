# Document Size Policy

Use this reference to keep AI_CONTEXT and `AGENTS.md` useful without becoming noisy.

## 1. Soft Size Targets

These are guidance, not hard limits:

- root `AGENTS.md`: 50-140 lines
- folder `AGENTS.md`: 25-80 lines
- `00_START_HERE.md`: 40-120 lines
- project overview/stack/structure docs: 40-140 lines each
- architecture/domain/feature/API/design/operation docs: 40-160 lines each
- module detail docs: 60-220 lines
- contract maps: as short as possible; split when one table covers unrelated contracts
- `99_CHANGELOG/AI_CHANGELOG.md`: small index only; one month row pointing to its latest daily record
- daily changelog entry: roughly 5-10 lines, with one `YYYY-MM-DD.md` record file per date
- changelog evidence: focused detail only; split unrelated topics into separate same-day evidence files

## 2. Split Rules

Split a document when:

- it mixes unrelated modules or audiences
- a table becomes hard to scan
- a module detail doc contains multiple independent contract maps
- folder rules repeat the same text already present in a parent `AGENTS.md`
- the reader would need to skim many unrelated details to make one change
- a daily changelog contains long experiment sequences, raw logs, or repeated validation details that belong in same-month evidence

Prefer an index/summary doc plus focused subdocs over one large catch-all document.

For changelogs, never split a date into per-change record files. Keep concise outcomes together in `YYYY-MM/YYYY-MM-DD.md` and move optional detail to `YYYY-MM/evidence/` according to `changelog-policy.md`.

## 3. Compression Rules

- Prefer tables, checklists, and short rules over prose.
- Link to related docs instead of repeating the same rule.
- Keep examples only when they prevent mistakes.
- Group repeated files by pattern, such as `etc/*.html`, instead of listing every ordinary leaf file.
- Keep file names only for entrypoints, contract boundaries, shared utilities, or high-risk files.

## 4. Required Content Still Wins

Do not omit safety-critical details just to stay short. If a contract, auth rule, migration rule, native rule, or external integration risk is important, include it and split the doc if needed.
