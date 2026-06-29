# Prompt Patterns

Use these prompts when invoking this skill in another project.

## Minimal Apply Request

```text
@project-ai-context-builder 를 적용해줘
```

The skill should infer language, project type, initialize/refresh/deepen mode, analysis strategy, output structure, and validation steps from the repository.


## Initial Repository Analysis

```text
$project-ai-context-builder

이 저장소를 분석해서 AI 주도 개발용 AI_CONTEXT와 AGENTS.md 체계를 생성해줘.
코드 수정, 기능 추가, 리팩터링, 설정 변경은 하지 말고 문서만 생성해.
기존 문서가 있으면 현재 코드 기준으로 새로 작성/갱신해.
확인된 사실과 추정은 구분하고, 불확실한 내용은 확인 필요로 표시해.
민감정보, 토큰, 비밀번호, 키 값은 문서에 원문으로 기록하지 마.
```

## React Web / Next.js Project

```text
$project-ai-context-builder

이 React/Next.js 웹 프로젝트를 분석해서 AI_CONTEXT와 루트/폴더별 AGENTS.md를 생성해줘.
라우팅, 페이지/컴포넌트, API client/generated 파일, 인증/세션, form validation, 디자인 시스템, responsive 규칙을 포함해줘.
코드 수정은 하지 말고 문서만 생성해.
```

## React Native Project

```text
$project-ai-context-builder

이 React Native 앱을 분석해서 AI 주도 개발용 AI_CONTEXT와 AGENTS.md를 생성해줘.
앱 부팅, navigation, screens, API context/generated client, Android/iOS/native 권한, assets, theme, build/signing 주의사항을 포함해줘.
민감정보와 signing/Firebase 값은 원문 기록하지 마.
```

## Backend API Project

```text
$project-ai-context-builder

이 백엔드 API 프로젝트를 분석해서 AI_CONTEXT와 AGENTS.md 체계를 생성해줘.
Controller/Service/Repository/Entity/DTO, API/예외/인증, DB/JPA/migration, transaction, scheduler/event 흐름을 포함해줘.
코드 수정은 하지 말고 문서만 생성해.
```

## Module Deepening

```text
$project-ai-context-builder

이미 생성된 AI_CONTEXT와 AGENTS.md를 기준으로, <module-or-folder> 하위 세부 패키지/폴더의 비즈니스 흐름을 더 깊게 분석해줘.
필요한 하위 AGENTS.md와 AI_CONTEXT/08_MODULE_DETAIL 문서를 현재 코드 기준으로 새로 작성/갱신해줘.
```

## Refresh Existing Docs

```text
$project-ai-context-builder

기존 AI_CONTEXT와 AGENTS.md가 오래되었을 수 있으니 현재 코드 기준으로 다시 분석해서 갱신해줘.
삭제나 코드 수정은 하지 말고, stale한 문서는 새 내용으로 정리해줘.
변경 이력은 AI_CONTEXT/99_CHANGELOG/AI_CHANGELOG.md에 남겨줘.
```
