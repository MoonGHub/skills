# Prompt Patterns

Use these prompts when invoking this skill in another project.

## Minimal Apply Request

```text
@project-ai-context-builder 를 적용해줘
```

The skill should infer language, project type, initialize/refresh/deepen mode, analysis strategy, output structure, and validation steps from the repository.

Default analysis should reach meaningful folder/work-area depth, record app-wide files and shared utilities in module detail docs, and avoid noisy per-file documentation.

When direct API/schema/config/route contracts are found, the result should include a compact contract map. Keep documents concise and split oversized module detail into focused subdocs.


## Initial Repository Analysis

```text
$project-ai-context-builder

이 저장소를 분석해서 AI 주도 개발용 AI_CONTEXT와 AGENTS.md 체계를 생성해줘.
코드 수정, 기능 추가, 리팩터링, 설정 변경은 하지 말고 문서만 생성해.
기존 문서가 있으면 현재 코드 기준으로 새로 작성/갱신해.
상위 폴더 요약에서 멈추지 말고 의미 있는 폴더/기능/모듈 단위까지 분석해.
파일 단위 전체 문서화는 하지 말고, 앱 전체에 영향 주는 핵심 파일/유틸은 module detail에 명시해.
화면/API/schema/config 간 직접 의존성이 확인되면 contract map을 만들어줘.
문서는 크기 가이드를 지켜 간결하게 작성하고, 너무 길어지면 focused subdoc으로 나눠줘.
확인된 사실과 추정은 구분하고, 불확실한 내용은 확인 필요로 표시해.
민감정보, 토큰, 비밀번호, 키 값은 문서에 원문으로 기록하지 마.
```

## React Web / Next.js Project

```text
$project-ai-context-builder

이 React/Next.js 웹 프로젝트를 분석해서 AI_CONTEXT와 루트/폴더별 AGENTS.md를 생성해줘.
라우팅, 페이지/컴포넌트, API client/generated 파일, 인증/세션, form validation, 디자인 시스템, responsive 규칙을 포함해줘.
파일 단위 전체 문서화는 하지 말고, app entrypoint, route/layout, API client, auth/session, store/context, theme/utils 같은 핵심 경계는 module detail에 정리해줘.
페이지/컴포넌트가 API 응답 필드나 route param에 직접 의존하면 contract map을 만들어줘.
코드 수정은 하지 말고 문서만 생성해.
```

## React Native Project

```text
$project-ai-context-builder

이 React Native 앱을 분석해서 AI 주도 개발용 AI_CONTEXT와 AGENTS.md를 생성해줘.
앱 부팅, navigation, screens, API context/generated client, Android/iOS/native 권한, assets, theme, build/signing 주의사항을 포함해줘.
파일 단위 전체 문서화는 하지 말고, app entrypoint, navigator, API boundary, context/store, native permission/signing-adjacent 경계는 module detail에 정리해줘.
screen/navigation/API contract가 직접 연결된 부분은 screen/API contract map으로 정리해줘.
민감정보와 signing/Firebase 값은 원문 기록하지 마.
```

## Backend API Project

```text
$project-ai-context-builder

이 백엔드 API 프로젝트를 분석해서 AI_CONTEXT와 AGENTS.md 체계를 생성해줘.
Controller/Service/Repository/Entity/DTO, API/예외/인증, DB/JPA/migration, transaction, scheduler/event 흐름을 포함해줘.
파일 단위 전체 문서화는 하지 말고, application entrypoint, security, global exception, transaction, migration, external client, shared utility 경계는 module detail에 정리해줘.
Controller/DTO/schema/API client/template 간 직접 의존성이 있으면 contract map을 만들어줘.
코드 수정은 하지 말고 문서만 생성해.
```

## Module Deepening

```text
$project-ai-context-builder

이미 생성된 AI_CONTEXT와 AGENTS.md를 기준으로, <module-or-folder> 하위 세부 패키지/폴더의 비즈니스 흐름을 더 깊게 분석해줘.
필요한 하위 AGENTS.md와 AI_CONTEXT/08_MODULE_DETAIL 문서를 현재 코드 기준으로 새로 작성/갱신해줘.
파일별 전체 목록은 만들지 말고, 의미 있는 하위 폴더와 핵심 파일/유틸/경계만 정리해줘.
새로 확인된 cross-boundary contract가 있으면 module detail에 contract map으로 반영해줘.
```

## Refresh Existing Docs

```text
$project-ai-context-builder

기존 AI_CONTEXT와 AGENTS.md가 오래되었을 수 있으니 현재 코드 기준으로 다시 분석해서 갱신해줘.
삭제나 코드 수정은 하지 말고, stale한 문서는 새 내용으로 정리해줘.
상위 요약이 얕으면 의미 있는 폴더/기능/모듈 단위까지 보강하고, 핵심 파일/유틸은 module detail에 반영해줘.
기존 문서에 빠진 contract map과 너무 큰 문서의 분할 필요성을 함께 점검해줘.
변경 이력은 AI_CONTEXT/99_CHANGELOG/AI_CHANGELOG.md에 남겨줘.
```
