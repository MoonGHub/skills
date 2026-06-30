# Fallback Strategy

Use this reference when no stack-specific analysis reference clearly matches the repository.

## 1. Detection

Infer the project shape from files, not assumptions:

- manifests and lockfiles
- source roots and entrypoints
- route, screen, command, job, or handler folders
- API/client/generated boundaries
- state/data/persistence folders
- config/profile/env files
- build/test/run scripts
- assets, styles, native, or deployment folders

If the stack remains unclear, write `확인 필요` and continue with the generic workflow.

## 2. Generic Analysis Areas

Document the current project using the closest applicable AI_CONTEXT structure:

- project purpose, users, stack, commands, and folder structure
- app/request/job flow from entrypoint to output
- module/feature ownership and dependency direction
- route/API/screen/command contracts
- data/state/persistence and migration/storage rules
- auth/security/config/env handling
- external integrations and risky boundaries
- tests, build, run, deployment, and troubleshooting

## 3. Generic Folder AGENTS

Create folder guides for meaningful work areas:

- app/module roots
- routes, screens, handlers, controllers, jobs, or command folders
- API/client/generated boundaries
- services, domain, data, persistence, repository, model, schema folders
- config/security/auth/env folders
- shared utilities, styles/theme, assets, tests, and integration folders

Avoid per-file docs and generated/vendor/build/cache output.

## 4. Generic Contract Maps

Create a contract map when a source area depends on another boundary:

- UI or scripts consume API/schema fields
- command/job payloads map to storage or external providers
- config/env keys control runtime behavior
- generated clients mirror backend contracts
- data models affect persistence, migrations, API, or UI

Use `references/contract-map-policy.md` for naming and content.

## 5. Safety

Do not invent framework-specific rules. Preserve confirmed commands and identifiers exactly. Mark unclear architecture, runtime behavior, deployment policy, or product intent as `확인 필요`.
