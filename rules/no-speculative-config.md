# No Speculative Configuration Rules

Keep configuration demand-driven, observable, and aligned with verified repository and consumer requirements.

## Demand-Driven Configuration

- Add or modify rules, plugins, parser options, environment flags, scripts, and workflow settings only for an active requirement.
- Prefer the smallest configuration that satisfies the current contract.
- Reuse repeated configuration values when a local abstraction makes the configuration clearer; avoid duplicating identical definitions.
- Remove configuration that has no current consumer, test, or documented public purpose.
- Do not add options, fallback branches, compatibility modes, or feature flags for hypothetical future needs.

## Match Patterns and Boundaries

- Make repository paths, file patterns, extensions, and ignore rules match actual files and supported boundaries.
- Use an existing source of truth for cross-cutting patterns and lists; avoid duplicating or independently maintaining them across configuration modules.
- Derive composite settings from established shared definitions when that preserves consistency.
- Use consumer-facing patterns only when they are part of a documented contract and covered by tests.
- Keep generated artifacts and external tool boundaries explicit rather than hiding them in broad patterns.

## Effective Configuration

- Remove dead settings that no supported consumer reads, including stale keys, unreachable branches, and values shadowed by later configuration.
- Ensure selectors, paths, and patterns match at least one supported target; remove entries that can never apply.
- Avoid no-op values that equal the tool's effective default unless the explicit value is required by a public contract or protects against a documented default change.
- Verify configuration through the tool's validation or effective-configuration output, or through a representative command that demonstrates the setting takes effect. File presence alone does not prove a setting is active.

## Verification

- Confirm that each non-obvious configuration option has a requirement or observable verification.
- Inspect configured paths and patterns against the repository's actual files and supported boundaries.
- Check for ignored, shadowed, unreachable, unmatched, or default-equivalent settings.
- Check that shared configuration values have one clear source of truth.
- Inspect the diff for unneeded packages or options; use the repository's normal verification commands and automation.
