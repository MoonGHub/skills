# Safety and Validation Rules

## Documentation Only Mode

When the user asks for AI_CONTEXT or AGENTS.md generation:

- Do not edit source code.
- Do not add features.
- Do not refactor.
- Do not change settings.
- Do not delete files.
- Do not modify generated API files, native generated output, migrations, package locks, or build artifacts.
- Create or update markdown documentation only.

If a problem is found in code, document it under `확인 필요` or `주의사항` instead of fixing it.

## Fact Discipline

Use these labels in docs:

- `확인된 사실`: directly observed in code/config/docs.
- `추정`: reasonable inference from structure or naming.
- `확인 필요`: cannot be proven locally or depends on operating/product policy.

Never present inferred architecture, content claims, route intent, backend contract, or operating policy as confirmed.

## Secret Handling

Do not copy values for:

- passwords
- tokens
- API keys
- private keys
- client secrets
- refresh tokens
- auth codes
- production IP allowlists when sensitive
- payment credentials or payloads
- Firebase/service-account values
- mobile signing, keystore, provisioning, certificate values
- real phone numbers, emails, personal identifiers when unnecessary

It is usually acceptable to document property/env key names and secret purpose without values.

## Generated/Vendor Exclusions

Avoid treating these as source unless explicitly relevant:

- `node_modules`, `.next`, `dist`, `build`, `coverage`
- `.gradle`, Gradle/Maven build output
- React Native `android/app/build`, `.cxx`, `ios/Pods`, `vendor/bundle`
- generated API clients/models except to document regeneration and ownership

## Suggested Validation Commands

Use commands appropriate to the repo. Examples:

```bash
find AI_CONTEXT -type f | sort
find . -name AGENTS.md -not -path '*/node_modules/*' -not -path '*/build/*' | sort
rg -n "password|passwd|secret|token|api[_-]?key|credential|client[_-]?secret|refresh[_-]?token|firebase|keystore|signing" AI_CONTEXT -g "*.md"
git status --short
```

When scanning, inspect matches carefully. Generic words such as `password` may appear in rules; the risk is recording actual values.

## Final Report

Mention:

- documentation-only scope
- generated/updated paths
- confirmed facts
- assumptions and `확인 필요`
- whether secret scan found risky literal values
- whether tests were skipped because no code changed
