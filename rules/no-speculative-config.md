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

## Verification

- Confirm that each non-obvious configuration option has a requirement or observable verification.
- Inspect configured paths and patterns against the repository's actual files and supported boundaries.
- Check that shared configuration values have one clear source of truth.
- Inspect the diff for unneeded packages or options; use the repository's normal verification commands and automation.
