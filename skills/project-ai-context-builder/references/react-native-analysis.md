# React Native Analysis Checklist

Use this reference for React Native/mobile apps, including cross-platform apps and apps with Android/iOS native folders.

## 1. Stack and Build

- package manager and Node engine
- React Native, React, TypeScript versions
- navigation library and root navigator files
- state/API context, generated API client, WebSocket/chat if present
- NativeWind/theme/design approach
- Firebase, push notification, storage, social login, WebView, image picker, permissions
- commands: start, android, ios, pod-install, build:android, gen-api, tsc, lint, test

## 2. Boot and Navigation

Document:

- app entrypoint and boot/splash flow
- auth gate and initial route reset logic
- navigator hierarchy and `RootStackParamList`
- screen groups and route params
- header exceptions or per-screen layout behavior

Rules:

- Keep route params and `RootStackParamList` aligned.
- Check all navigate calls when adding or renaming screens.
- Do not bypass auth/onboarding gates without explicit requirement.

## 3. API, Auth, and State

Document:

- API context/provider and generated API file
- token/header injection and logout behavior
- error alert/toast pattern
- query/mutation hooks and refetch/navigation side effects
- backend contract regeneration command

Rules:

- Treat generated API files as generated output.
- Do not document token/auth payload/payment payload values.
- Check chat/WebSocket or push-token auth when auth state changes.

## 4. Native Android/iOS

Document:

- Android/iOS folders and whether they are source vs generated/vendor output
- permissions, intent/deep link, app icons/splash, signing/build config
- CocoaPods, Gradle, Firebase/GoogleService files, native modules
- simulator/device assumptions and build commands

Rules:

- Do not change signing, keystore, provisioning, Firebase config, or permissions casually.
- Do not record signing/Firebase/private key values.
- Separate source files from generated native build output such as `.cxx`, `build`, and `Pods`.

## 5. UI, Theme, and Assets

Document:

- shared components, module components, screen-specific components
- theme tokens, typography, NativeWind class patterns
- image/media upload constraints and asset registration
- responsive/device rules and safe-area behavior

Rules:

- Prefer existing shared components and typography wrappers.
- Check Android/iOS behavior for file/media/WebView/permission changes.

## 6. Folder AGENTS Targets

Consider docs for:

- `screens`, screen subdomains, navigation files
- `components`, `components/module`, `components/ui`
- `contexts`, `hooks`, `libs`, `utils`, `types`, `theme`, `assets`
- `android`, `ios`, native config areas
