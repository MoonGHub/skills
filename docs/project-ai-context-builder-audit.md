# Project AI Context Builder Audit

This document records the current review state for `project-ai-context-builder`. It is for maintainers; the runtime skill guidance lives in `skills/project-ai-context-builder/SKILL.md` and `skills/project-ai-context-builder/references/`.

## Scope

- Skill: `project-ai-context-builder`
- Purpose: create or refresh AI-led development context docs so future sessions can continue work with less context reload.
- Outputs: root `AGENTS.md`, adaptive `AI_CONTEXT`, folder-level `AGENTS.md`, and `AI_CHANGELOG`.
- Supported project shapes: backend/API services, React/Vite/Next.js web apps, React Native/mobile apps, content/static web sites, and mixed repositories.

## Requirement Check

| Requirement | Status |
| --- | --- |
| Short invocation such as `@project-ai-context-builder` triggers the full workflow | 충족 |
| Detect user/project language and write docs in that language | 충족 |
| Initialize missing docs from current repository files | 충족 |
| Refresh existing docs by re-scanning the project | 충족 |
| Deepen selected modules/folders without file-by-file noise | 충족 |
| Generate root and folder-level `AGENTS.md` | 충족 |
| Generate adaptive `AI_CONTEXT` docs and changelog | 충족 |
| Separate confirmed facts, assumptions, and `확인 필요` | 충족 |
| Avoid source/config/generated/runtime changes unless explicitly requested | 충족 |
| Avoid recording secret values, tokens, keys, or credentials | 충족 |
| Include frontend design/UI/responsive guidance when applicable | 충족 |
| Keep service-specific names and local filesystem paths out of published skill content | 충족 |
| Report quality-check results when the skill runs | 충족 |

## Purpose Fit

| Item | Level | Reason |
| --- | --- | --- |
| 적용 수준 | 상 | The workflow covers initialize, refresh, and deepen modes and ties each mode to concrete outputs. |
| 프로젝트 분석 수준 | 상 | The skill requires stack, structure, modules, flows, API/state/data, build/test/run, and high-risk area analysis. |
| AI_CONTEXT 완성도 | 상 | The output contract requires start, project, architecture/feature/domain, development, operation, module-detail, and changelog docs when relevant. |
| AGENTS.md 실용성 | 상 | Root and folder guide templates define role, rules, do-not items, related context, and check-together paths. |
| 컨텍스트 지속성 | 상 | Required reading order, impact checks, changelog updates, and folder guides are explicit. |
| 안전성/보안성 | 상 | Documentation-only rules, secret handling, and generated/vendor exclusions are explicit. |
| 변경 추적성 | 상 | The workflow requires changelog updates and final reporting of generated paths, validation, and remaining `확인 필요`. |
| 컨텍스트 효율 | 상 | Progressive references keep `SKILL.md` compact and discourage noisy per-file documentation. |

## Notes

- The skill intentionally does not include a skill-local `README.md`; this keeps the skill folder focused on executable instructions and references.
- `references/quality-check.md` is the runtime checklist used in final reports.
