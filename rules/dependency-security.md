# Dependency Security Rules

Review dependencies for supply-chain risk, ongoing maintenance, and reproducible resolution using the conventions of the current repository.

## Dependency Screening and Lifecycle

- Evaluate maintenance status, release cadence, license, and security advisory history before introducing a dependency.
- Prefer native platform capabilities and existing lockfile dependencies over new external packages.
- Add a dependency only when active code, tests, build tooling, or a documented contract uses it.
- Remove a dependency when its last consumer is removed.
- Keep dependencies in the manifest category that matches their actual role.
- Prefer reputable, actively maintained dependencies with compatible upstream support.
- Reject dependencies with unmaintained transitive trees, unresolved compatibility warnings, or unverified installation scripts.

## Lockfile and Versions

- Follow the repository's versioning policy; pin exact versions when deterministic execution requires it.
- Maintain the ecosystem's lockfile as the authoritative resolution record when one is used.
- Bound compatibility ranges to supported runtimes and consumers.
- Keep package manifests free of speculative, unused, and duplicate dependencies.

## Vulnerability Policy

- Run dependency audits when requested or required by the repository's established verification policy; do not add them as an implicit local step.

## Verification

- Inspect manifest and lockfile changes for unauthorized packages, unjustified version ranges, or unconsumed dependencies.
- Resolve findings from requested dependency and unused-code analysis rather than suppressing them.
