# Changelog Policy

Use this reference whenever creating, updating, validating, or migrating project changelogs.

## Structure

```text
AI_CONTEXT/99_CHANGELOG/
├── AI_CHANGELOG.md
└── 2026-08/
    ├── 2026-08-11.md
    ├── 2026-08-12.md
    └── evidence/
        └── 2026-08-12-deployment-validation.md
```

- Keep `AI_CHANGELOG.md` as a stable reading/search index, never a detailed history.
- Use one `YYYY-MM` level, not `YYYY/YYYY-MM`, and one `YYYY-MM-DD.md` record per calendar day.
- Put all meaningful changes completed that day in the daily file; do not create monthly README or per-change files.
- Create month and evidence folders only when they have content. Use the documented project timezone or the execution environment timezone.

The index contains the reading rule, a warning not to load all history by default, a rule to search targeted month folders by topic/identifier before opening records, and one row per month linked to that month's latest daily record:

```md
| Month | Latest record |
| --- | --- |
| 2026-08 | [2026-08-12](2026-08/2026-08-12.md) |
```

## Daily Entry

Append sections in completion order. Merge a same-day follow-up into the same topic; put a later correction in the later date instead of rewriting valid history.

```md
# 2026-08-12

## backend — result explanation contract

- 변경: owner-only result API와 delayed media 조회 계약을 연결했습니다.
- 이유: 새 세션에서도 저장된 결과를 복원하기 위해 변경했습니다.
- 영향: result API, generated client, private media ticket에 영향을 줍니다.
- 검증: 관련 backend test와 frontend typecheck를 통과했습니다.
- 관련 문서: `AI_CONTEXT/04_API/RESULT.md`
- 확인 필요: production media delivery는 미검증입니다.
- 상세 근거: [통합 검증](evidence/2026-08-12-result-validation.md)
```

Use the documentation language. Every entry needs change, reason, impact, and final validation concepts. Add related docs, unresolved items, and evidence only when useful. Keep an ordinary entry near 5-10 lines and record final pass/fail/skip plus important gates, not raw output.

## Selection and Evidence

Record durable changes to user flow, interface/API/IPC, DB/schema, generated contracts, route/auth/native behavior, security/recovery, architecture/ownership, build/env/deployment/operations, important recurrence prevention, or AI_CONTEXT contracts.

Do not record formatting-only edits, exhaustive file lists, repeated counts, inconsequential attempts, cleanup repetition, or raw Git/CI logs. Update current-state docs first and link them rather than copying their explanation.

Create `YYYY-MM/evidence/YYYY-MM-DD-<short-kebab-topic>.md` only for detailed diagnosis, experiments, threat analysis, migration proof, benchmarks, or validation with future audit value. Link it from the daily entry; keep the concise outcome in the daily file. Move detail there if a daily file grows, but never split the date into multiple record files.

## Ownership and Legacy Migration

Record detail once at the lowest project that owns the change. Root records only repository-wide or cross-project contracts and links service records rather than duplicating them.

For a legacy monolith, inventory date headings without loading the whole file by default, migrate one date block at a time, merge same-date items, preserve final contract/reason/impact/validation/unresolved facts, and move only durable detail to evidence. Preserve ambiguous unique content as `확인 필요`. Verify date coverage, links, and retained decisions before replacing the monolith with the index.

## Check

- path and date shape are exact
- index is navigation only and points to each month's latest record
- meaningful entries contain the four required concepts
- evidence is optional, linked, same-month, and free of private values
- root and child projects do not duplicate detail
