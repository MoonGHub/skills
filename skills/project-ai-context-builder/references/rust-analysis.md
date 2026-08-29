# Rust / Cargo Analysis

Use this reference only for Rust crates or Cargo workspaces. Record repository-specific contracts, not general Rust instruction.

## 1. Cargo Topology and Toolchain

Inspect root and crate `Cargo.toml`, `Cargo.lock`, `rust-toolchain*`, `.cargo/config.toml`, and confirmed CI/build configuration.

Document:

- workspace `members`, `default-members`, `exclude`, `resolver`, shared dependencies/lints/profiles, and dependency direction
- crate path, role, kind (`lib`, `bin`, `proc-macro`, `cdylib`, etc.), and actual entrypoint
- edition, `rust-version`/workspace-inherited MSRV, pinned toolchain/components, and build targets when confirmed
- `Cargo.lock` tracking/use policy and whether canonical commands require `--locked` or `--frozen`

A Cargo workspace alone does not imply separate project contexts. If crates show independent responsibility or release/deploy/runtime lifecycles, apply `multi-project-patterns.md` rather than duplicating its boundary test here.

## 2. Entrypoints and Runtime

Trace `src/main.rs`, `src/lib.rs`, `[[bin]]`, examples used operationally, and server/worker/command bootstrap. Record public module or crate boundaries only when they affect callers.

For async systems, identify the runtime, task owner, blocking boundary, channels/shared state, cancellation, graceful shutdown, and signal flow. For libraries and CLIs, identify the public API or command/input/output boundary. Avoid module-by-module inventories.

## 3. Features, Targets, and Generation

Document features only when they alter public API, artifact, native dependency, or an operational command. Include default/optional features, dependency-edge activation, `default-features = false`, workspace feature propagation, target-specific `cfg`, and confirmed mutually exclusive constraints when applicable. Record the combinations actually used by CI or deployment; do not assume `--all-features` is the canonical gate.

When present, inspect `build.rs`, its `rerun-if-*` inputs, source references such as `include!(concat!(env!("OUT_DIR"), ...))`, protobuf/OpenAPI/bindgen generation, and native linking. Do not traverse Cargo-managed `OUT_DIR`/`target` output as source. Record generation inputs, generated boundary, consumers, build/regeneration command, and hand-edit rule. Treat a proc macro separately as a compile-time public contract only when its derive/attribute behavior affects consuming crates.

## 4. Interface, Data, and Errors

Record only externally relevant contracts:

- HTTP/RPC/CLI/library input and output boundaries
- `serde` rename/tag/default/optional behavior that affects wire compatibility
- internal error ownership versus conversion to external status, response, exit code, or diagnostic
- database driver/ORM/query layer, pool, transaction and migration ownership
- schema/model/interface propagation and external provider payload transformations

Inspect patterns such as `thiserror`, `anyhow`, custom errors, `serde`, SQLx/Diesel/SeaORM, Axum/Actix/Rocket/Tonic only when present; do not infer architecture from a dependency name alone.

## 5. Unsafe and FFI

When present, identify high-risk `unsafe` functions/traits/impls/blocks, their `SAFETY` invariants, owner, and callers. For FFI, record ABI and `repr(C)` boundaries, allocation/free ownership, lifetime/nullability, threading/callback constraints, panic boundary, native library/linker requirements, and binding/header source of truth.

If no unsafe/FFI is found in the repository-owned source that was searched, record that bounded fact in one line at most. Do not make claims about dependencies or expanded macros, and do not create an empty detail document.

## 6. Validation and Operations

Inspect Cargo aliases and repository wrappers such as `.cargo/config.toml`, `xtask`, `just`, and `cargo nextest` when present. Record commands exactly as configured, including package, workspace, feature, lock, and target scope:

- formatting: `cargo fmt` or repository wrapper
- linting: `cargo clippy` and the confirmed lint policy
- unit, integration, documentation, ignored, or feature-specific tests
- build/release, migration, benchmark, generation, and cross-compilation commands when used

Distinguish a command found in files from a command executed successfully. For cross-compilation, record confirmed target triple, components, linker/native dependencies, container or `cross` usage, and produced artifact. Capture runtime arguments, environment key names, ports, migration/startup order, health checks, and shutdown behavior without values.

## 7. AGENTS Candidate Folders

Recursively evaluate workspace and crate roots, `src` module trees, `bin`, handler/router/API, service/use-case, domain/model, repository/persistence/database, runtime/task/worker, error, migration, build/generation, unsafe/FFI/native-integration, examples, benches, and test boundaries when present. Do not stop at a crate root or `src` when distinct modules own separate responsibilities. Module names are discovery signals, not proof of an architecture; apply the Inclusion Test and file-count placement rule in `scope-policy.md`.

## 8. Rust-Specific Output

- Project structure: compact crate/role/kind/entrypoint/dependency table.
- Architecture: request/command/job and async/task or public crate-boundary flow.
- Service projects: reuse domain/API/database sections; CLI, daemon, library, embedded/WASM, or systems projects use only applicable module/interface/data sections.
- Development/operation: exact edition/MSRV/toolchain plus feature/target/lock-aware commands and portable prerequisites.
- Detail only when needed: public crate, runtime, build generation, persistence, unsafe/FFI, native linking, or integration-test boundary.

Apply `scope-policy.md` for folder guides and exclusions rather than restating the common rules here.

Create a contract map only when a confirmed relationship merits it, such as schema/serde/protobuf → handler/client/storage, feature/target → public API or artifact, FFI ABI → callers/bindings, or build input → generated consumer. A normal Cargo dependency graph does not need a separate map.
