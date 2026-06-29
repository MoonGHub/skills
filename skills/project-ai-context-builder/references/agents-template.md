# Folder AGENTS.md Template

Use this template for folder-level guidance. Keep each file short and local to the folder.

```md
# AGENTS.md

## Role

이 폴더의 역할을 1-3문장으로 설명한다.

## Key Files

- `ImportantFile.tsx`
- `ImportantClass.java`
- `ImportantConfig.ts`

## Business Flow

확인된 핵심 흐름을 짧게 정리한다. 단순 폴더면 생략 가능하다.

## Rules

- 수정 시 반드시 지켜야 할 규칙.
- 인접 계층, route/navigation, API contract, generated file, 이벤트, 응답 포맷, 보안, DB, native, 디자인 영향 확인 지점.

## Do Not

- 이 폴더에서 하면 안 되는 것.
- 계층 위반, 민감정보 노출, 생성 파일 수동 수정, 임의 응답/route/native/DB/design 변경 등.

## Related Context

- `AI_CONTEXT/...`

## Check Together

- 함께 확인해야 하는 폴더/파일.
```

## Root AGENTS.md Contract

Root `AGENTS.md` is the top-level Codex instruction file, not a generic human-only contributor guide. Use this shape unless an existing project-specific format is clearly better.

```md
# AGENTS.md

## Role

이 파일은 Codex가 이 프로젝트에서 작업하기 전 반드시 읽는 최상위 지침이다. 이 저장소/앱의 기술 스택, 모듈 구성, 핵심 책임을 한두 문장으로 요약한다.

## Required Reading

작업 전 다음 문서를 순서대로 읽는다.

1. `AGENTS.md`
2. `AI_CONTEXT/00_START_HERE.md`
3. `AI_CONTEXT/<DEVELOPMENT_SECTION>/AI_DEV_RULE.md`
4. 작업 대상 폴더의 가장 가까운 `AGENTS.md`
5. 관련 `AI_CONTEXT` 문서

## Rules

- 코드 수정 전 관련 문서를 확인하고 영향 범위를 먼저 파악한다.
- 코드 또는 문서 수정 후 의미 있는 변경 이력을 `AI_CONTEXT/99_CHANGELOG/AI_CHANGELOG.md`에 기록한다.
- API 변경 시 관련 API contract/error/auth 문서를 확인한다.
- DB 변경 시 DB/JPA/migration 문서를 확인한다.
- UI 변경 시 design/component/responsive 문서를 확인한다.
- native 변경 시 Android/iOS/permission/signing 문서를 확인한다.
- 기존 응답 포맷, 예외 처리, 계층 구조, route guard, generated file, 디자인 시스템을 임의로 변경하지 않는다.
- 확인된 사실과 추정은 구분하고, 불확실한 내용은 `확인 필요`로 표시한다.
- 보안 정보, 비밀번호, 토큰, 키 값은 문서나 답변에 그대로 기록하지 않는다.

## Do Not

- 명시 요청 없이 코드 리팩터링, 기능 추가, 설정 변경, DB schema/native 설정/라우팅 구조 변경을 하지 않는다.
- 생성 API 파일을 수동으로 광범위하게 수정하지 않는다.
- 기존 계층/의존 방향/인증 정책/상태 전이를 임의로 바꾸지 않는다.
- Entity/DB 변경을 migration 검토 없이 진행하지 않는다.
- 사용자 변경사항을 되돌리지 않는다.

## Related Context

- 프로젝트 개요: `AI_CONTEXT/01_PROJECT/`
- 아키텍처: `AI_CONTEXT/02_ARCHITECTURE/`
- 도메인/기능/콘텐츠: `AI_CONTEXT/03_*/`
- API/연동: `AI_CONTEXT/04_*/`
- DB/디자인/native: `AI_CONTEXT/05_*/`
- 개발 규칙: `AI_CONTEXT/<DEVELOPMENT_SECTION>/`
- 운영/실행: `AI_CONTEXT/<OPERATION_SECTION>/`
- 모듈 상세: `AI_CONTEXT/<MODULE_DETAIL_SECTION>/`
- 변경 이력: `AI_CONTEXT/99_CHANGELOG/AI_CHANGELOG.md`

## Check Together

- 작업 유형별로 함께 확인할 폴더와 문서를 나열한다.
```

## Coverage Heuristics

Create folder AGENTS when any of these are true:

- folder contains backend controller/service/repository/entity/config/scheduler/event listener/DTO/tests
- folder contains frontend route/page/screen/component/api/client/generated wrapper/hook/context/store/style/theme/asset/test code
- folder is a module or app boundary
- folder has business meaning or frequent future edits
- folder has security, data, API, external integration, native, payment, upload, or operational risk

Do not create noisy AGENTS for generated code, build output, dependency/vendor directories, empty folders, or folders with no independent responsibility.

## Generated File Guidance

When generated files exist, document them as generated and point to the regeneration command. Examples:

- Orval: generated API hooks/models should usually not be hand-edited.
- swagger-typescript-api: `Api.ts` should usually be regenerated.
- React Native native build outputs should not be documented as source folders.
