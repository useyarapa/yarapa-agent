# No Suppression Rules

Resolve diagnostics and runtime failures at their root cause. Preserve useful signals instead of hiding them with bypasses or unrelated configuration changes.

## Type Resolution

- Use the language's standard type narrowing and validation mechanisms to make assumptions explicit.
- For missing third-party type information, use an authoritative upstream definition or a narrow local declaration in the repository's established location.
- Report conflicting type definitions or unfixable third-party declarations before proposing workarounds.

## Linter Resolution

- Refactor code to satisfy diagnostic rule invariants at their source.
- Resolve implementation defects directly; keep bypass directives and rule overrides limited to documented, necessary cases.
- Report unresolved rule conflicts or configuration defects before proposing workarounds.

## Error Semantics and Diagnostics

- Preserve runtime failure visibility: let errors surface directly to the caller or process boundary with complete diagnostic context.
- Handle errors only when adding diagnostic context, recovering definitively, or transforming at an architectural boundary; eliminate empty catches and concealing fallback values.
- Retain root causes across abstraction layers rather than wrapping failures in generic catch-all errors.

## Verification

- Confirm diagnostics on touched files resolve using the repository's supported tooling.
- Verify error handling preserves root causes and surfaces failures without silent suppression.
