# Depth and Exclusion Policy

Use this reference before creating or refreshing `AI_CONTEXT` and folder-level `AGENTS.md`.

## 1. Depth Standard

Apply the same depth standard in `Initialize`, `Refresh`, and `Deepen` modes.

Do not stop at top-level or one-depth summaries when the repository has meaningful work areas below them. Analyze down to folder-level responsibilities for features, modules, routes, screens, services, repositories, API clients, state, design systems, native folders, config, tests, and high-risk integrations.

Do not document every file. Use file names only when a file is a central entrypoint, shared boundary, generated boundary, cross-cutting utility, or high-risk integration.

## 2. Include as Work Areas

Create or refresh folder `AGENTS.md` when a folder has independent responsibility or is likely to guide future AI work:

- app/module roots and source roots
- backend controller, service, facade, repository, entity, domain, DTO, config, security, scheduler, event, migration, and test folders
- frontend route, page, screen, component module, API client, generated boundary, hook, context, store, form, validation, style, theme, asset, and test folders
- React Native `android`, `ios`, permission, native module, signing-adjacent, navigation, screen, context, theme, and asset folders
- shared utility folders for date, money, upload, storage, logging, masking, encryption, permission, error handling, or formatting
- folders with auth, external integration, payment, file upload, data persistence, native build, or operational risk

## 3. Exclude by Default

Do not create source-responsibility docs for:

- dependency, generated, build, cache, and coverage output such as `node_modules`, `.next`, `dist`, `build`, `.gradle`, `target`, `coverage`, `Pods`, `.cxx`, and `vendor`
- ordinary leaf components with no independent contract
- simple type-only folders or trivial helper folders already explained by the parent guide
- empty folders and folders whose only role is obvious from the parent `AGENTS.md`
- generated API/model internals as a file-by-file inventory
- static images, fonts, and media assets as file-by-file descriptions
- literal values from secret-bearing files, credentials, signing material, tokens, keys, or production-only config

## 4. Document as Exceptions

Document an otherwise excluded or file-level item in module detail when it affects project-wide behavior or future change risk:

- entrypoints such as `main.tsx`, `App.tsx`, `layout.tsx`, `Application.java`, root navigator, or bootstrapping files
- route, navigation, layout, middleware, or guard boundaries
- API clients, generated-code boundaries, mutators, fetch wrappers, interceptors, and common error handlers
- auth/session providers, global stores, contexts, query clients, or app-wide hooks
- theme roots, design tokens, base UI components, responsive rules, and component-system contracts
- Spring Security config, global exception handling, transaction boundaries, schedulers, event listeners, and external clients
- JPA base entity, auditing, migration ownership, and DB change boundaries
- React Native native folders, permissions, signing-adjacent config, Firebase/Google service boundaries, and native modules
- cross-cutting utilities for date, money, upload, storage, logging, masking, encryption, permission, and validation

## 5. Decision Test

Include a folder or file reference when at least one answer is yes:

- Will future AI work likely modify this area or inspect it for impact analysis?
- Does it define a contract used by many other folders?
- Would changing it affect routing, API behavior, auth, state, database, native behavior, design consistency, build/run behavior, or external integrations?
- Does the area have special rules that are not obvious from the parent folder?

Exclude or summarize at parent level when:

- the folder has no independent responsibility
- the role is obvious from the parent guide
- the contents are generated, vendored, cached, or build output
- documenting it would become a noisy file inventory

For generated boundaries, document ownership, regeneration command if discoverable, and hand-edit restrictions. Do not list generated internals one by one.
