# Quality Check

Use this checklist before the final report. Report only items that apply to the analyzed repository. Rate each item as `상`, `중`, `하`, or `확인 필요`, and add one short reason.

## Result Checklist

- 적용 수준: requested mode was handled correctly (`Initialize`, `Refresh`, or `Deepen`) and the generated/updated docs match the requested scope.
- 프로젝트 분석 수준: stack, structure, entrypoints, modules, flows, API/state/data boundaries, build/test/run commands, and high-risk areas were analyzed from current files.
- AI_CONTEXT 완성도: start guide, project overview, architecture/feature/domain docs, development rules, operation docs, module detail docs, and changelog are present when relevant.
- AGENTS.md 실용성: root and folder guides provide role, rules, do-not items, related context, and check-together paths that help future work.
- 컨텍스트 지속성: a new session can resume work by following the reading order, impact checks, folder guides, and changelog.
- 안전성/보안성: docs avoid source changes, generated/vendor output as source ownership, and literal secret values.
- 변경 추적성: generated/updated paths, validation result, skipped tests reason, and remaining `확인 필요` are reported.
- 컨텍스트 효율: docs are concise, avoid noisy per-file coverage, and place detailed guidance only where it helps future work.

## Reporting Rule

Include a `품질 체크 결과` section in the final answer. Keep it short; use a compact table or bullets.
