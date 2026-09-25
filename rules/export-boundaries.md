# Export Boundaries Rules

Keep public APIs explicit and stable while preserving encapsulation between packages and modules.

## Canonical Public Contract

- Maintain the repository's designated public entrypoints as the canonical export contract for each package or module.
- Export complete, supported interfaces that consumers can rely on; keep implementation details private.
- Do not expose internal helpers, registries, or third-party implementation objects as public API without an explicit contract.
- Keep private sibling types, constants, and helpers out of public export surfaces unless consumers need them as part of the documented API.

## Package Manifest Boundaries

- Where package metadata controls exports, list supported entrypoints explicitly and map them to the appropriate build outputs.
- Do not expose broad wildcards or internal directories through package metadata.
- Publish the type information and other metadata required by the package ecosystem for every supported export.
- Treat build outputs as generated artifacts and edit their source inputs instead.

## Module Encapsulation

- Keep module-internal types, constants, and utilities close to the implementation that owns them.
- Share cross-module values through an established, intentional interface rather than reaching into another module's internals.
- Encapsulate third-party dependencies behind the module or package that owns their use.

## Verification

- Inspect the repository's public export metadata to ensure only supported entrypoints are exposed.
- Verify that public signatures remain compatible with the documented contract and ecosystem conventions.
- Confirm generated outputs correspond to their source definitions.
