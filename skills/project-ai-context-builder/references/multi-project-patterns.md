# Multi-Project Documentation Patterns

This reference summarizes reusable documentation patterns for backend services, React web apps, content/static web sites, and React Native/mobile apps. Use these as generic examples, not as project-specific facts for a new repository.

## Root AGENTS Pattern

Root `AGENTS.md` should state:

- the project identity and responsibility
- required reading order: root `AGENTS.md`, `AI_CONTEXT/00_START_HERE.md`, project AI dev rule, closest folder `AGENTS.md`, related AI_CONTEXT docs
- impact checks before code changes
- changelog update rule
- API/UI/native/DB/design docs to read for each change type
- generated file policy
- secret handling rule
- user-change preservation rule
- forbidden changes
- related context index
- check-together map by work area

## React Web Patterns

Observed useful sections:

- `03_FEATURE`: feature overview, page flow, component map, term dictionary
- `04_API`: API client, backend contract, auth session/token, error handling
- `05_DESIGN`: design system, layout/component/table/form/responsive patterns
- `08_MODULE_DETAIL`: routes/pages, API/generated client, components, state/hooks/utils

Folder guides should cover route constants, guards, generated API, fetch/axios mutators, React Query hooks, forms/zod, upload limits, UI wrappers, enum labels, status badges, table columns, env handling.

## React Native Patterns

Observed useful sections:

- `02_ARCHITECTURE`: app boot flow, navigation rule, state/API rule
- `03_FEATURE`: screen flow, component map, feature overview
- `04_API`: API client, backend contract, auth token, error handling
- `05_NATIVE`: Android, iOS, permissions, build/signing checks
- `06_DESIGN`: design system, theme, screen component, device responsiveness
- `09_MODULE_DETAIL`: screens, contexts/API, components, native assets

Folder guides should cover `StackNav.tsx`, `RootStackParamList`, screens, generated `libs/Api.ts`, contexts, hooks, Android/iOS, permissions, assets, theme, Firebase/signing secrets.

## Content/Static Web Site Patterns

Observed useful sections:

- `03_CONTENT`: content overview, page section flow, CTA link map, term dictionary
- `04_INTEGRATION`: external links, backend impact, SEO metadata
- `05_DESIGN`: visual design, layout, motion/3D, responsive rules
- `08_MODULE_DETAIL`: app routes, home sections, shared components, 3D/assets

Folder guides should cover static export constraints, metadata, CTA links, GNB/Footer, section order, images/models, client-only 3D/canvas behavior, and unverified content claims.

## Backend Patterns

Observed useful sections:

- `03_DOMAIN`, `04_API`, `05_DATABASE`, `08_MODULE_DETAIL`
- Root rules should call out API contract propagation to clients, DB/JPA/Flyway, auth/authorization, response/error format, transaction/layer rules, and high-risk state transitions.

## Reusable Prompt/Response Lessons

- Ask for documentation-only analysis when building context docs.
- Ask to rewrite stale docs from current code when existing docs are present.
- Ask for module-by-module deepening after the first pass.
- Require final reports to list generated docs, confirmed facts, assumptions, `확인 필요`, validation, and next recommended area.
