# React Native Analysis

Use this reference only for React Native/mobile projects with Metro and Android/iOS targets.

## Stack and Boot

Inspect manifests/lockfiles, `App.*`, navigation roots, Metro/Babel/TypeScript config, `android/`, `ios/`, API/state providers, permissions, assets/theme, native modules, tests, and confirmed build configuration.

Record package manager and versions, app bootstrap/splash/auth gate, navigator hierarchy, `RootStackParamList` or equivalent, initial/reset behavior, state/API ownership, generated-client source, and canonical start/typecheck/lint/test/generation/device/build commands.

## Screen, API, and State Contracts

Trace representative screen flows through navigation params, contexts/hooks/store, generated or handwritten clients, request/response fields, local persistence, permissions, media, WebView, push/chat, and success/error/navigation effects.

Document route-param alignment, auth/logout/token-refresh side effects, query/mutation/refetch behavior, offline/storage behavior when present, and API regeneration boundaries. Create a map only for confirmed screen/navigation/API/native-config dependencies.

## Native Boundaries

Identify source versus generated native output, permissions and deep links, native modules, Gradle/CocoaPods ownership, Firebase/Google service integration boundary, app identifiers, signing/provisioning ownership, icons/splash, target variants, and simulator/device assumptions.

Capture platform differences, source-of-truth files, and coordinated checks without copying signing or service values. Exclude `.cxx`, native build output, Pods, and generated client/model internals.

## UI, Theme, and Assets

Record shared UI/typography wrappers, tokens/theme or NativeWind conventions, safe-area and device-size behavior, accessibility, asset registration, media constraints, and platform-specific component behavior. Avoid ordinary screen/component inventories.

## Output Focus

- `01_PROJECT`: React Native/toolchain/package manager, app targets and commands.
- `02_ARCHITECTURE`: boot, navigation, auth/state/API direction.
- `03_FEATURE`, `04_API`, `05_NATIVE`, `06_DESIGN`: applicable current contracts.
- Development/operation: portable Android/iOS prerequisites, variants, permissions, generation, gates, and artifacts.
- Module detail/folder AGENTS: navigation root, screen domains, API/state providers, native permission/module/signing-adjacent areas, theme/assets, and tests with distinct rules.
