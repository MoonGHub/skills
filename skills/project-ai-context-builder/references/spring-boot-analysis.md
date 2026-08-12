# Spring Boot Analysis

Use this reference only for Java/Spring Boot or closely related Gradle/Maven services.

## Structure and Build

Inspect `settings.gradle*`, `build.gradle*`, `pom.xml`, wrappers, `src/main/java`, `src/test`, resources, migrations, templates/static content, and confirmed generated-source configuration.

Record Java/Spring versions, modules and dependency direction, `@SpringBootApplication` entrypoints, package roots, active build tool, test libraries, database/migration tools, external clients, containers, and canonical commands. Distinguish a command found in files from one executed successfully.

## Configuration and Runtime

Map profile activation, datasource/migration behavior, scheduling conditions, security/session/filter configuration, logging, and external property groups by key name and owner. Identify startup order, required infrastructure, health endpoints, and deployment artifact when confirmed.

## Request and Domain Flow

Trace representative flows across:

- Controller URL/method and request/response DTO
- Service/facade use case, transaction boundary, events, and state transitions
- Repository/Querydsl/JDBC access and important search rules
- Entity/VO/enum relationships, cascade/fetch/orphan removal, auditing, and migration ownership
- exception/advice mapping, response envelope, authentication and authorization
- scheduler/listener/external-client behavior and retry/idempotency when present
- server-rendered template or static consumers of backend fields

Verify actual dependency direction instead of imposing Controller/Service/Repository conventions on a different architecture.

## High-Risk Boundaries

Prioritize source anchors for security matcher/authority mapping, global exception/response format, transaction boundaries, entity/schema migration, schedulers/events, external integrations, generated clients, shared date/money/upload/masking utilities, and irreversible state transitions.

Create a contract map only for confirmed DTO/schema/template/client/config propagation. Keep full endpoint or schema detail in the owning API/database document.

## Output Focus

- `01_PROJECT`: Java/Spring/build versions, modules, entrypoints, commands.
- `02_ARCHITECTURE`: request flow, dependency and transaction rules.
- `03_DOMAIN`, `04_API`, `05_DATABASE`: only confirmed domain/interface/persistence contracts.
- Development/operation: profiles, portable prerequisites, migrations, canonical gates, deployment/startup.
- Module detail/folder AGENTS: business-heavy packages and non-obvious security, advice, event, scheduler, migration, external-client, generated, and test boundaries only.
