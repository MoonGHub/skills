# Contract Map Policy

Use this reference when screens, templates, API clients, config, generated boundaries, schemas, or integrations directly depend on another layer's contract.

## 1. When to Create

Create a contract map when a future AI session must know "if this contract changes, what else breaks?"

Common triggers:

- templates, screens, components, or scripts directly read API response fields
- API clients, generated models, mutators, interceptors, or fetch wrappers shape requests/responses
- route params, query params, navigation params, or layout guards are used as contracts
- env/profile/config keys affect runtime behavior
- database schema/entity changes propagate to API, UI, migrations, or external integrations
- external provider payloads are transformed before storage or display

Do not create a map for ordinary internal helper calls or folders already explained by a nearby `AGENTS.md`.

## 2. Where to Put It

Place maps under the module detail section, usually `AI_CONTEXT/08_MODULE_DETAIL/` or the project's equivalent.

Suggested names:

- `WEB_TEMPLATE_API_MAP.md`: server-rendered templates with inline API calls
- `FRONTEND_API_CONTRACT_MAP.md`: React/Next pages, components, hooks, and API clients
- `SCREEN_API_MAP.md`: mobile screens and backend/API contract
- `API_CLIENT_CONTRACT_MAP.md`: generated clients, mutators, wrappers, interceptors
- `CONFIG_CONTRACT_MAP.md`: env/profile/config keys and runtime owners
- `<MODULE>_CONTRACT_MAP.md`: module-specific contract with many callers

## 3. What to Include

Keep maps compact. Prefer a table with:

- caller: screen/template/component/service/config file or work area
- contract: endpoint, DTO/schema, route param, env key, table/entity, generated file, or external payload
- owner: Controller/service/client/config/domain module
- consumed fields or request fields
- change rule: what to check before modifying
- related files/folders to inspect together
- `확인 필요` when the relation cannot be proven fully

## 4. What to Avoid

- Do not copy secret values, auth payloads, real user data, or production-only credentials.
- Do not list every file in a feature folder.
- Do not document generated internals line by line; document the generated boundary and regeneration rule.
- Do not invent contracts from naming alone. Mark uncertain mappings as `확인 필요`.

## 5. Maintenance Rule

When API responses, route params, generated clients, entity/schema fields, env keys, external payload mappings, or UI field usage change, update the relevant contract map and `AI_CONTEXT/99_CHANGELOG/AI_CHANGELOG.md`.
