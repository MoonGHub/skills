# Execution Contract

Use this reference whenever the user gives a short request such as `@project-ai-context-builder 를 적용해줘`.

## 1. Language Detection

Detect the documentation language from available signals:

- current user request language
- existing root `AGENTS.md`, `README`, `AI_CONTEXT`, and project docs
- dominant comments or user-facing docs
- system/developer context only as a fallback

Rules:

- Write docs in the detected user/project language.
- Preserve code identifiers, package names, commands, file names, routes, component names, and technology names as-is.
- If language signals conflict, prefer the user's current request language.

## 2. Mode Selection

Choose exactly one main mode, then execute it thoroughly.

### Initialize

Use when no meaningful `AI_CONTEXT` and root/folder `AGENTS.md` exist.

- Analyze from current project files.
- Create root `AGENTS.md`.
- Create adaptive AI_CONTEXT structure.
- Create folder-level `AGENTS.md` for meaningful work areas.

### Refresh

Use when docs already exist or appear partially generated.

- Re-scan the whole project.
- Compare current docs against current code structure.
- Improve stale, shallow, missing, or misleading docs.
- Preserve useful project-specific numbering and naming.
- Update changelog.

### Deepen

Use when the user names a module/folder or asks for more detail in a specific area.

- Read existing docs first.
- Analyze the target module and adjacent dependencies.
- Add/refresh module detail docs and nearest folder `AGENTS.md`.
- Do not explode to per-file docs unless a file is an entrypoint, generated boundary, or risky integration.

## 3. Strategy Self-Check Before Writing

Before writing docs, internally verify:

- Does the strategy help a new AI session resume work without conversation context?
- Does it cover project structure, stack, architecture, domain/feature flow, API, data/state, security/auth, build/run/test, and high-risk areas?
- Does it choose frontend design docs when the project has UI?
- Does it avoid source-code edits and generated/vendor output?
- Does it keep docs concise enough to be reusable?
- Does it separate confirmed facts, assumptions, and `확인 필요`?

If the answer is weak, adjust the strategy before writing.

## 4. Depth Control

Good depth:

- root, app/module, major feature/domain packages
- route/page/screen groups
- controller/service/repository/domain/config groups
- API client/generated boundary folders
- shared components, form modules, hooks/context/store, styles/theme/assets
- native Android/iOS folders when relevant

Too deep:

- one `AGENTS.md` per ordinary file
- generated output folders
- dependency/vendor/build folders
- tiny folders whose only role is already obvious from the parent

## 5. Post-Write Self-Review

After writing docs, re-check:

- root `AGENTS.md` follows the required shape
- `00_START_HERE` gives a clear next-session reading order
- AI dev rules enforce changelog and nearest AGENTS reading
- folder AGENTS coverage is neither too sparse nor too noisy
- frontend projects include design/responsive/component guidance
- secret scan does not reveal literal sensitive values
- final report includes remaining `확인 필요` and next steps
