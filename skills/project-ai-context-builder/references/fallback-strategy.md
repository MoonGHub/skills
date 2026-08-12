# Fact-Based Fallback

Use this reference only when no specialist reference matches.

Infer project shape from manifests/lockfiles, source roots, entrypoints, routes or commands, interface/client/generated boundaries, state/data/persistence, config, build/test/run scripts, assets, deployment, and tests. If the shape remains unclear, record `확인 필요` and continue with confirmed facts.

Document only applicable areas:

- purpose, users, stack, ownership, commands, and portable prerequisites
- entrypoint-to-output request, command, job, or event flow
- module responsibility and dependency direction
- interface/route/screen/payload contracts
- state, persistence, migration, and external-integration boundaries
- auth/security/config handling and high-risk areas
- tests, build, run, deploy, recovery, and known unknowns

Create folder guides only for independently responsible work areas. Create a contract map only for a proven boundary. Do not invent framework conventions, product intent, runtime policy, or deployment behavior from names alone.
