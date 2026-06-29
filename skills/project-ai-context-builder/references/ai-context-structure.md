# AI_CONTEXT Structure

Create concise markdown documents. Prefer rules, relationships, flows, and warnings over long explanations. Preserve an existing project-specific numbering scheme if one already exists.

## Universal Docs

Every project should have:

- `00_START_HERE.md`: one-line summary, reading order, mandatory checks, area references, AI principles
- `01_PROJECT/OVERVIEW.md`: purpose, users, core features, confirmed facts and `확인 필요`
- `01_PROJECT/STACK.md`: language, framework, runtime, libraries, package manager, infra
- `01_PROJECT/STRUCTURE.md`: module/folder responsibilities
- development rules: `06_DEVELOPMENT` or project-specific equivalent
- operation/build docs: `07_OPERATION`, `08_OPERATION`, or project-specific equivalent
- module detail docs: `08_MODULE_DETAIL` or `09_MODULE_DETAIL`
- `99_CHANGELOG/AI_CHANGELOG.md`

## Backend/API Variant

Use when the project is a backend service:

- `02_ARCHITECTURE`: layer, request flow, dependency, transaction rules
- `03_DOMAIN`: domain overview, entity relation, business flow, term dictionary
- `04_API`: API convention, error response, authorization
- `05_DATABASE`: DB overview, JPA/ORM/migration/query rules

## React Web Variant

Use when the project is a React/Vite/Next web app:

- `02_ARCHITECTURE`: app flow, routing rule, state/API rule, dependency rule
- `03_FEATURE`: feature overview, page flow, component map, term dictionary
- `04_API`: API client, backend contract, auth session/token, error handling
- `05_DESIGN`: design system, layout/component/table/form/responsive rules
- `08_MODULE_DETAIL`: routes/pages, API client/generated files, components, state/hooks/utils

## React Native Variant

Use when the project is a React Native app:

- `02_ARCHITECTURE`: app boot flow, navigation rule, state/API rule, dependency rule
- `03_FEATURE`: feature overview, screen flow, component map, term dictionary
- `04_API`: API client, backend contract, auth token, error handling
- `05_NATIVE`: Android rule, iOS rule, permission rule, build/signing check
- `06_DESIGN`: design system, theme pattern, screen component pattern, device responsiveness
- `07_DEVELOPMENT`, `08_OPERATION`, `09_MODULE_DETAIL` when following the mobile numbering pattern

## Content/Static Web Site Variant

Use when the project is a content, static, documentation, or presentation-oriented web site:

- `02_ARCHITECTURE`: app flow, routing/static export, asset rendering, dependency rule
- `03_CONTENT`: content overview, page section flow, CTA link map, term dictionary
- `04_INTEGRATION`: external links, backend impact, SEO metadata
- `05_DESIGN`: visual design system, layout, motion/3D, responsive rules
- `08_MODULE_DETAIL`: app routes, home sections, shared components, assets/3D detail

## Required AI Development Rules

Include these in the project AI dev rule doc:

- Read `AI_CONTEXT/00_START_HERE.md` first.
- Read root `AGENTS.md` before work.
- Read the closest folder `AGENTS.md` for the target area.
- Understand impact before code changes.
- Do not change API response, generated client, routing, auth, DB, native, or design contract casually.
- Check migration rules before Entity/DB changes.
- Check native docs before Android/iOS/permission/signing changes.
- Preserve existing architecture and generated-file boundaries.
- Update `AI_CONTEXT/99_CHANGELOG/AI_CHANGELOG.md` after work.
- Refresh folder `AGENTS.md` if it becomes stale.
