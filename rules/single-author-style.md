# Single Author Style Rules

Treat each cohesive application, package, or component as if one careful engineer owns it. Keep conventions consistent within that boundary while respecting intentional differences in language, runtime, and framework across the repository.

## Sibling Precedent

- Match representative siblings in the same category and owning project before deciding layout, naming, exports, helper placement, composition, error handling, or abstraction level.
- Default to the language and ecosystem's standard idioms when no applicable local pattern exists.
- When patterns conflict, follow the most specific applicable project instruction and closest relevant precedent; explain the chosen convention when the conflict affects the design.

## New Components and Workspace Scope

Before creating a new application, package, service, or peer module:

1. Read repository-level and nearest project-level instructions, manifests, and configuration.
2. Inspect representative siblings in the same workspace or project and follow their architecture and public interface patterns.
3. Use the declared language, runtime, framework, lifecycle commands, and verification steps for that project; follow its package-manager conventions where applicable.
4. Update workspace registration, automation, release configuration, and documentation when the new component requires them.

## Structural Symmetry and Cohesion

- Keep declarations and implementation sections predictable among siblings with the same responsibility, following local structure where it exists.
- Keep execution flow collocated and direct; introduce separate files or helpers only when multiple callers share them.

## Declarative Naming and Types

- Use one term for one concept within the owning project across filenames, symbols, configuration, tests, and documentation.
- Name parallel symbols with matching grammatical structure that describes the domain contract.
- Keep types, data models, and function signatures concrete and readable where the language provides them; follow that language's established idioms.
- Write comments only to capture non-obvious domain intent, technical constraints, or upstream workarounds; let identifiers explain mechanics.

## Scoped Changes

- Keep edits within the requested component and its necessary consumers or workspace metadata.
- Use the owning project's configured linters and formatters as the source of truth for code style.
- Make cross-project or repository-wide convention changes explicit in the task scope.

## Verification

- Inspect relevant siblings in the owning project to verify structure, naming, interfaces, and abstraction conventions.
- Confirm interfaces remain direct without speculative abstractions or wrappers.
- Verify changes stay within the requested scope and include any necessary workspace references without incidental refactoring.
