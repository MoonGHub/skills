# Contract Map Policy

Read this reference only after confirming a dependency where a change on one boundary can break another.

## Create a Map When

- UI, template, CLI, job, or client consumes an API/schema/route field
- a generated client, serializer, mutator, interceptor, or external-payload transform shapes a contract
- env/profile/feature/target keys change runtime behavior or artifacts
- entity/schema/migration changes propagate to interfaces or consumers
- native, FFI/ABI, code-generation, or cross-project edges require coordinated changes

Do not map ordinary helper calls or copy a manifest dependency graph.

## Ownership and Content

Keep one canonical map at the lowest common owner. Root maps contain cross-project edges only; internal details stay with the owning project.

Prefer a compact table with only applicable columns:

| Owner/source | Contract/invariant | Consumers | Change impact/check | Source anchors | Canonical docs |
| --- | --- | --- | --- | --- | --- |

Use repository-relative anchors. Mark unproven relations `확인 필요`. Link the owning subject document for full request/response, schema, or domain detail rather than copying it.

Suggested names include `FRONTEND_API_CONTRACT_MAP.md`, `SCREEN_API_MAP.md`, `CONFIG_CONTRACT_MAP.md`, `FFI_ABI_CONTRACT_MAP.md`, and `<MODULE>_CONTRACT_MAP.md`; use a name that matches the actual boundary.

## Maintenance

When an owner, consumer, invariant, mapped field/key, generated boundary, feature/target, or source anchor changes, update the owning current-state doc and this one map, then record the result in the daily changelog. If an anchor disappears, revalidate that mapped area rather than the whole repository.

Do not include secret values, real private data, raw payload dumps, generated internals, or a file inventory.
