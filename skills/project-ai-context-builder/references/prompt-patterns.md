# Prompt Patterns

Read this reference only when the user asks how to invoke the skill.

## Minimal

```text
$project-ai-context-builder 를 적용해줘.
```

The skill infers language, mode, project shape, targeted reading, output, and validation.

## Useful Options

Append only what changes the default:

```text
- 현재 문서가 오래되었을 수 있으니 source anchor와 변경 영역을 기준으로 증분 갱신해줘.
- <module-or-folder>와 직접 연결된 계약만 더 깊게 분석해줘.
- 전체 감사가 필요하니 저장소 전체를 현재 코드 기준으로 다시 분석해줘.
- 기존 수동 문서는 보존하고 스킬 관리 문서만 안전하게 갱신해줘.
- 새 장비에서 시작할 수 있도록 bootstrap과 최소 검증 gate를 특히 확인해줘.
```

## Rust Example

```text
$project-ai-context-builder

이 Rust/Cargo 프로젝트를 AI 주도 개발 문서로 정리해줘.
workspace/crate 소유권, entrypoint와 async runtime, feature/target, build.rs/generated 경계,
interface/data/error 계약, unsafe/FFI, 정확한 cargo 검증 범위와 portable operation을 현재 파일에서 확인해줘.
일반 Rust 설명이나 모듈 전체 목록은 만들지 말고, 새 세션이 관련 영역만 읽도록 라우팅해줘.
```
