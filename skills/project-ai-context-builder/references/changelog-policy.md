# Changelog Policy

Use this reference whenever creating, updating, reading, validating, or migrating project changelogs.

Contents: [output](#1-output-contract), [index](#2-index-contract), [daily record](#3-daily-record-contract), [selection](#4-record-selection), [evidence](#5-evidence), [ownership](#6-multi-project-ownership), [migration](#7-legacy-migration), [validation](#8-validation).

## 1. Output Contract

Use one year-month folder level and one record file per calendar day:

```text
AI_CONTEXT/99_CHANGELOG/
├── AI_CHANGELOG.md
└── 2026-08/
    ├── 2026-08-11.md
    ├── 2026-08-12.md
    └── evidence/
        └── 2026-08-12-deployment-validation.md
```

- Keep `AI_CHANGELOG.md` as a small, stable index. Do not append detailed changes to it.
- Name month folders `YYYY-MM`; do not nest them as `YYYY/YYYY-MM`.
- Name the only daily record `YYYY-MM-DD.md`. Put every meaningful change completed that day in that file.
- Do not create a monthly `README.md` or one record file per change.
- Create month and `evidence/` folders only when they have content.
- Use the documented project timezone; otherwise use the execution environment timezone.

## 2. Index Contract

Keep `AI_CHANGELOG.md` limited to:

- reading and search rules
- a month table whose row links to that month's latest daily record
- a warning not to load the full history by default

The subject-specific AI_CONTEXT documents describe current state. Changelog files describe what changed. Read a relevant daily record only when recent context or a past decision is needed, and read evidence only for deeper investigation.

Suggested month table:

```md
| Month | Latest record |
| --- | --- |
| 2026-08 | [2026-08-12](2026-08/2026-08-12.md) |
```

## 3. Daily Record Contract

Append sections in completion order. Update the existing section for a same-day follow-up to the same topic. Record a correction made on a later date in that later date's file instead of rewriting valid history.

```md
# 2026-08-12

## backend — JLPT 결과 해설 계약

- 변경: owner-only 결과 해설 API와 지연 media 조회 계약을 연결했습니다.
- 이유: 새 세션에서도 저장된 결과 해설을 복원하기 위해 변경했습니다.
- 영향: 결과 API, frontend generated client, private media ticket에 영향을 줍니다.
- 검증: 관련 backend test와 frontend typecheck를 통과했습니다.
- 관련 문서: `AI_CONTEXT/04_API/JLPT.md`
- 확인 필요: 실제 production media delivery는 미검증입니다.
- 상세 근거: [통합 검증 기록](evidence/2026-08-12-jlpt-validation.md)
```

- Require change, reason, impact, and validation concepts (`변경`, `이유`, `영향`, `검증` in Korean); write their labels in the detected documentation language.
- Include related docs, `확인 필요`, and evidence only when applicable.
- Keep an ordinary entry to roughly 5-10 lines. Report only final pass/fail/skip and the relevant gates, not raw logs.

## 4. Record Selection

Record meaningful changes to features or user flows; API, IPC, DB, schema, generated, route, auth, or native contracts; security, recovery, architecture, ownership, build, env, deployment, operations, important bug-prevention rules, or AI_CONTEXT contracts.

Do not record formatting-only work, exhaustive file lists, repeated test counts or cleanup results, inconsequential failed attempts, or raw Git/CI logs. Link to current subject docs instead of repeating current-state explanations.

## 5. Evidence

Create evidence only when detailed experiments, failure diagnosis, threat analysis, migration proof, benchmarks, or long validation results have future diagnostic or audit value.

- Put it at `AI_CONTEXT/99_CHANGELOG/YYYY-MM/evidence/YYYY-MM-DD-<short-kebab-topic>.md`.
- Allow multiple evidence files per date and link them from the relevant daily section.
- Keep the daily file authoritative for the concise outcome; do not duplicate the summary in evidence.
- If a daily file becomes long, move explanations and experiment sequences to evidence instead of creating another record file.
- Omit evidence when Git, CI, or the concise daily record is sufficient. If unsure whether a unique confirmed fact may be lost, preserve it in evidence and mark uncertainty as `확인 필요`.

## 6. Multi-Project Ownership

Record a change once at the lowest project that owns it. Root changelogs record only cross-project or repository-wide contracts. Service-internal changes belong only to the service changelog. For a cross-boundary change, summarize only the root-level contract at root and link to service records instead of copying their details.

## 7. Legacy Migration

When a large monolithic `AI_CHANGELOG.md` is found:

1. Inventory date headings and process one date block at a time instead of loading the entire file by default.
2. Merge same-date entries into `YYYY-MM/YYYY-MM-DD.md`.
3. Preserve final contract, reason, impact, final validation, and unresolved items in concise sections.
4. Move only important diagnostic or audit detail to same-month evidence. Preserve ambiguous unique facts there as `확인 필요` rather than deleting them.
5. Verify date coverage, relative links, and retained unique decisions before replacing the monolith with the small index.

Do not add an automatic migration script. Migration requires project-aware judgment.

## 8. Validation

- Confirm paths match `YYYY-MM/YYYY-MM-DD.md`; reject `YYYY/YYYY-MM`, monthly `README.md`, and per-change record files.
- Confirm each meaningful entry has change, reason, impact, and final validation.
- Confirm `AI_CHANGELOG.md` contains navigation rather than detailed history.
- Confirm evidence is optional, linked, same-month, and contains no secret values or real private data.
- In multi-project repositories, confirm root and service records do not duplicate the same details.
