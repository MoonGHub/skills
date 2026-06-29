# Spring Boot Analysis Checklist

Use this reference when the repository is Java/Spring Boot or appears to contain Gradle/Maven modules.

## 1. Project Structure

- Detect Gradle/Maven: `settings.gradle`, `build.gradle`, `pom.xml`, wrapper files.
- Detect multi-module layout and module dependency direction.
- Locate Spring Boot entrypoint classes with `@SpringBootApplication`.
- Identify package roots under `src/main/java` and `src/test`.
- Inspect `src/main/resources`, `templates`, `static`, migration folders, and generated sources.

## 2. Stack

Record confirmed versions and libraries from build files:

- Java version
- Spring Boot version
- Spring Security, Web MVC, Validation
- JPA/Hibernate, Querydsl, JDBC
- Flyway or Liquibase
- Database driver
- Thymeleaf or frontend asset approach
- Test libraries
- External SDK/API clients
- Docker or compose files

Use `확인 필요` when version or runtime DB cannot be proven from files.

## 3. Configuration

Analyze without copying secret values:

- `application.yml`, `application-*.yml`, `.properties`
- active profile strategy
- datasource keys, DB type, ddl-auto, migration settings
- logging levels and file paths
- scheduler profiles
- security/session/IP/filter settings
- external API property groups

Document property names and intent, not secret values.

## 4. Domain and Code Flow

For each major package:

- Controller URL, HTTP methods, request/response shape
- Service responsibilities and transaction boundaries
- Repository and Querydsl search conditions
- Entity relationships, enums, cascade/fetch/orphanRemoval
- Events/listeners and audit/activity log flow
- Scheduler jobs and profile conditions
- DTO conversion location
- Template/static dependencies if server-rendered pages exist

## 5. Architecture Rules

Confirm and document:

- Controller must not accumulate business logic.
- Service owns use cases and transactions.
- Repository/persistence owns data access only.
- Entity changes require migration review.
- API response/error format must not be changed casually.
- Security matcher and role/authority mapping must be checked before API changes.

## 6. Tests and Operations

Find commands from wrapper/build files and existing docs:

- build command
- test command
- run command and profile examples
- docker/compose startup if present
- common local failures: DB, migration, env vars, external API credentials

If not verified by execution, write `명령 확인됨, 실행은 확인 필요`.
