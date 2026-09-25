# Single Author Style Rules

Write code as if one careful engineer owns the entire repository. Sibling code must share structure, naming, ordering, idioms, and abstraction level unless verified technical requirements dictate otherwise.

## Sibling Precedent

- Match the dominant local pattern of representative sibling files in the same category before deciding layout, naming, exports, helper placement, composition, error handling, or abstraction level.
- Default to standard ecosystem idioms when no local dominant pattern exists.
- Stop and confirm before introducing a new convention when existing implementations conflict.

## New Package and Sibling Pre-Flight

Before creating a new package or peer module:

1. Read representative siblings and their manifests and configuration first.
2. Follow the established file architecture, composition, and public entrypoint patterns.
3. Match shared lifecycle commands and supported verification steps.
4. Update affected workspace metadata, automation, release configuration, and documentation in the same change.

## Structural Symmetry and Cohesion

- Follow predictable file skeletons: arrange constants, types, helpers, implementations, and exports in a uniform section order across sibling files.
- Keep execution flow collocated and direct; introduce separate files or helpers only when multiple callers share them.

## Declarative Naming and Types

- Use one term for one concept across filenames, symbols, configs, tests, and documentation.
- Name parallel symbols with matching grammatical structure describing domain contract rather than mechanical implementation.
- Keep types, data models, and function signatures concrete and readable; follow the language's established idioms.
- Write comments only to capture non-obvious domain intent, technical constraints, or upstream workarounds; let identifiers explain mechanics.

## Scoped Changes

- Confine edits strictly to requested files.
- Rely on configured linters and formatters as the source of truth for code styling.
- Make repository-wide convention changes explicit in the task scope.

## Verification

- Inspect representative siblings to verify the change matches established structure, naming, export, and abstraction conventions.
- Confirm types and interfaces remain direct without speculative abstractions or wrappers.
- Verify changes remain confined to requested files without incidental refactoring.
