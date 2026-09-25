# Current State Authority Rules

Use the current repository state as the implementation authority; use Git history as evidence for investigation.

## Source of Truth

For implementation decisions, use this order of authority:

1. Explicit current user requirements
2. Current working tree
3. Current tests, contracts, schemas, and configuration
4. Current runtime behavior and logs
5. Official upstream documentation
6. Git history as historical evidence only

## Deleted and Reverted Code

- Treat code absent from the current working tree as intentionally removed unless current evidence shows otherwise.
- Restore, copy, port, adapt, reconstruct, or derive an implementation from deleted or reverted code only when the user explicitly requests restoration of historical code.
- Treat code removed because it was buggy, incorrect, obsolete, rejected, or being rewritten as rejected.
- Do not use rejected historical code as a reference implementation, implementation baseline, shortcut for rebuilding functionality, evidence that the previous design was correct, or justification for restoring the previous architecture.

## Git History Investigation

- Inspect Git history to identify when behavior changed, locate regression boundaries, understand why code changed or was removed, investigate previous bugs, discover rejected approaches, understand architectural decisions, or compare historical and current behavior.
- Use commands such as `git log`, `git show`, `git blame`, `git diff`, `git bisect`, `git log -S`, and `git log -G` for investigation.
- Establish the proven cause before making the smallest correct change against the current codebase.
- Treat historical code as evidence about the past. Finding it does not authorize restoring or reusing it.

## Rewrite Process

When rewriting functionality:

1. Inspect the current working tree.
2. Establish the current requirements and contracts.
3. Inspect current tests and configuration.
4. Reproduce or verify the current problem when applicable.
5. Implement against the current state; use any historical implementation only to understand what was attempted and why it changed or failed.
6. Complete the rewrite only after the checks in Verification pass.

## Conflict Resolution

- When Git history conflicts with current requirements, tests, contracts, architecture, configuration, or the current working tree, the current state wins unless the user explicitly instructs otherwise.
- Do not infer that code should be restored merely because it existed before. Determine why it existed, why it changed or disappeared, and what the current system requires.

## Verification

- Confirm implementation decisions follow the source-of-truth order.
- Pair each historical finding with the current working tree and identify the revision consulted; check the target revision explicitly if `HEAD` may have moved.
- For rewrites, confirm relevant current tests pass and runtime behavior satisfies the current contract.
