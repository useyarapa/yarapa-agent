# No Anti-Patterns Rules

Avoid recurring engineering anti-patterns in local automation, CI, tool execution, and implementation code.

## Hook and Execution Order

- Run mutating tools in a deterministic order, with verification after changes are applied.
- Keep local hooks fast and reliable. Run remote or network-dependent checks in CI unless the repository explicitly requires them locally.
- Use portable automation compatible with the repository's supported environments; document any required platform-specific behavior.

## Toolchain and Runner Parity

- Use the repository's declared package manager and locally available tools rather than downloading or selecting alternate runners.
- Prefer direct, discoverable project commands; remove wrappers that only forward arguments without adding behavior.

## System and Algorithm Assumptions

- Derive parsing and validation from documented formats instead of incidental assumptions such as fixed identifier lengths, operating systems, or working directories.

## Verification

- Inspect automation changes for unexpected network access in local workflows.
- Confirm commands use the repository's established toolchain and supported environments.
- Confirm mutating steps run in a stable order and verification follows them.
