# React Web / Next.js Analysis

Use this reference only for React, Vite, Next.js, dashboards, and React-based content/static sites.

## Stack and Build

Inspect `package.json`, lockfile/workspace configuration, framework config, TypeScript config, route roots, styling/design setup, API generation config, tests, and deployment/static-export settings.

Record package manager and versions, React/Next/Vite mode, App/Pages/custom router, state/data/form libraries, generated-client owner, canonical dev/build/lint/typecheck/test/generation commands, artifact/deploy mode, and portable runtime prerequisites.

## Routing, State, and Interfaces

Trace representative flows across route/page/layout, guards, feature components, hooks/store/context, forms/validation, API client/mutator/interceptor, backend fields, and success/error/navigation effects.

Capture non-obvious contracts:

- path constants, route/query params, layouts, middleware, and public/private guards
- server/client component or static-export boundaries
- session/cookie/header ownership and logout/error behavior
- generated API/model source and regeneration command
- form schema ↔ request type ↔ UI label/status/table meaning
- uploads/media limits and external-provider transformations

Create a contract map only where a page/component/hook directly consumes a field, route param, generated model, schema, or config key.

## UI and Content

Document existing component wrappers, design tokens, typography, layout/table/form patterns, responsive breakpoints, accessibility conventions, asset ownership, and motion/3D client-only constraints when present.

For content/static sites, capture page/section order, CTA/link ownership, SEO/metadata/OG, export/hosting constraints, and claims that need product confirmation. Do not duplicate copy or inventory ordinary components/assets.

## AGENTS Candidate Folders

Recursively evaluate app/project and source roots, `app`/`pages`/route/layout groups, feature domains, component modules and design-system roots, API/client/generated boundaries, hooks/context/store, forms/validation, `lib`/`utils`, styles/theme, middleware/auth/session, and test/e2e boundaries. Do not stop at `src`, `app`, `pages`, or `components` when distinct descendants exist. Names are discovery signals, not automatic inclusion; apply the Inclusion Test and file-count placement rule in `scope-policy.md`.

## Output Focus

- `01_PROJECT`: framework/package manager, route roots, build/deploy mode.
- `02_ARCHITECTURE`: app boot, routing/layout, state/data/API direction.
- `03_FEATURE` or `03_CONTENT`, `04_API` or `04_INTEGRATION`, `05_DESIGN`: only applicable current contracts.
- Development/operation: portable setup, env-key names, generation and minimum gates.
- Module detail/folder AGENTS: route groups, auth/session, API/generated boundary, state providers, design-system roots, forms, high-risk utilities, and tests with distinct rules.
