# Project Type Detection

Detect the project shape before choosing the AI_CONTEXT structure.

## Backend/API Indicators

- `build.gradle`, `settings.gradle`, `pom.xml`, `src/main/java`
- `@SpringBootApplication`, `@RestController`, `@Entity`, migration folders
- Typical docs: `03_DOMAIN`, `04_API`, `05_DATABASE`

## React Web Indicators

- `package.json` with `react`, `vite`, `react-router-dom`, `@tanstack/react-query`, Orval, axios, Tailwind, HeroUI, Radix, etc.
- Route folders such as `src/page`, `src/pages`, `src/routes`, `src/app`
- API generated files such as `generated.ts`, `model/*.ts`, `Api.ts`, `gen-api.js`, Orval or swagger-typescript-api config
- Typical docs: `03_FEATURE`, `04_API`, `05_DESIGN`

## Next.js Indicators

- `next` dependency, `next.config.*`, `src/app` or `pages`
- App Router layouts/pages, metadata, route handlers, static export settings
- If version is newer than model knowledge may cover, inspect installed docs or local source when available.

## React Native Indicators

- `react-native` dependency, `android`, `ios`, Metro config, `StackNav.tsx`, `App.tsx`
- native env/config, Firebase, permissions, image picker, WebView, navigation
- Typical docs: `03_FEATURE`, `04_API`, `05_NATIVE`, `06_DESIGN`

## Content/Static Web Site Indicators

- Next/Vite site focused on content sections, CTA links, SEO, static export, motion/3D/assets
- Typical docs: `03_CONTENT`, `04_INTEGRATION`, `05_DESIGN`

## Monorepo or Multi-Project Workspace

- Multiple independent apps under a `source`, `apps`, `packages`, or workspace root
- Create a root orientation only if useful, then analyze each app with its own AGENTS/AI_CONTEXT.
- Preserve app-specific package manager and build commands.
