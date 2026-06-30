# React Web / Next.js Analysis Checklist

Use this reference for React, Vite, Next.js, React web apps, dashboards, and content/static web sites.

## 1. Stack and Build

- package manager: pnpm, yarn, npm, bun
- React/Next/Vite/TypeScript versions
- route system: React Router, Next App Router, Pages Router, custom route arrays
- UI/design libraries: Tailwind, SCSS, HeroUI, Radix, shadcn-style wrappers, CSS modules
- state/data: React Query, context, Zustand/Redux, custom hooks
- forms/validation: react-hook-form, TanStack Form, zod, custom validation
- generated API: Orval, swagger-typescript-api, OpenAPI fetcher, axios mutator
- commands: dev, build, preview/start, lint, typecheck, test, gen-api

## 2. Routing and Pages

Document:

- route entry files and path constants
- auth/public/private guard rules
- layout hierarchy and shell components
- popup/modal route conventions
- page-to-feature mapping
- route params and query params that act as contracts

Rules:

- Do not hardcode route strings when constants exist.
- Check guards before changing auth-sensitive pages.
- For Next.js static export, do not add server-only features without checking export constraints.

## 3. API Client and Backend Contract

Document:

- API client entrypoint and generated files
- request mutator/fetch wrapper/interceptor
- token/cookie/session storage
- error alert/toast handling
- query/mutation hook pattern
- regeneration command and generated files that should not be hand-edited
- contract maps for pages/components/hooks that directly consume API fields, route params, generated models, or config/env keys

Rules:

- Treat generated API/model files as generated output.
- Update docs when backend contract changes.
- Update relevant contract maps when request/response fields, route params, generated models, env keys, or UI field usage changes.
- Never log or document token, env, payment, Firebase, or credential values.

## 4. Components, Forms, and UI

Document:

- shared UI components and wrappers
- domain module components
- form validation schema, request body type, mutation success behavior
- table/list/detail patterns, status badges, enum labels
- upload/media constraints
- responsive/design token rules

Rules:

- Prefer existing component wrappers and design tokens.
- Keep backend contract, zod/form schema, and UI labels aligned.
- Do not change enum labels/status badges/table column meaning without domain confirmation.

## 5. Content/Static Web Sites

Document when relevant:

- section order and CTA map
- SEO/metadata/OG rules
- static export or deployment constraints
- image/3D/motion assets and client-only rendering requirements
- external links and policy/recruit/contact claims requiring confirmation

Rules:

- Mark unverified content claims as `확인 필요`.
- Check asset path and license context before reusing images/models.
- Avoid adding backend/server behavior to static sites without architecture review.

## 6. Folder AGENTS Targets

Consider docs for:

- route/page folders
- API/generated/client folders
- components, components/ui, components/module, form folders
- hooks, contexts, store, libs/lib, utils/util, type/types
- styles/theme, public/assets/images/models
- tests/e2e if present
