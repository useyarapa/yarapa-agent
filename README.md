# Yarapa Agent Docs

Yarapa Agent Docs is a library of reusable Markdown rules for developers and teams who use coding agents. Each file focuses on an engineering concern—such as testing, package boundaries, configuration, or dependency changes—that you can review and adapt for your own repository.

This repository is a source library, not an installer or agent plugin. It does not add rules to your project or load them into an agent automatically. You choose which rules fit, adapt them to your codebase, and place them where your coding tool reads project instructions.

The rule text is designed to work across models. File discovery, metadata, scoping, and import behavior depend on the coding tool, its version, and its settings.

## Quick start

1. **Identify your coding tool.** Check its current documentation to find which project instruction files it reads and how it handles nested or path-specific rules.
2. **Inspect your repository.** Read its existing instructions, manifests, supported runtimes, commands, tests, and representative code. Reuse established project conventions.
3. **Choose only relevant rules.** Use the catalog below to find a rule whose purpose and prerequisites match your change or your team's ongoing policy. You do not need to adopt the entire library.
4. **Adapt the rule.** Replace general references with your project's actual tools and boundaries. Remove anything that conflicts with existing requirements or repeats another instruction.
5. **Add it to the agent's instruction system.** Copy the selected Markdown into a supported project instruction file, or use a documented import mechanism. Do not assume that a link to a file or a `rules/` directory is loaded automatically.
6. **Confirm and review.** Use your tool's context or instruction view when available, then try a representative task. Examples include `/context` in Claude Code, `/instructions` in Copilot CLI, Cursor's Active Rules view, and `/memory show` in Gemini CLI. Keep the adopted instructions in version control and update them when the project changes.

For a requirement that must always be enforced, choose a deterministic mechanism that matches the requirement: use a linter for static code constraints, tests for behavior, CI to gate proposed changes, or hooks and tool permissions to control local actions. Markdown rules guide an agent; they do not guarantee that a command is blocked or run.

## Choose rules for your task

Review each rule's scope before adopting it. Some are useful across a repository; others only apply when changing a particular part of a project.

| Area | Rule | Use it when |
| --- | --- | --- |
| Workflow and project scope | [`current-state-authority.md`](rules/current-state-authority.md) | Investigating existing behavior, rewriting functionality, or deciding whether historical code should be reused. |
| Workflow and project scope | [`new-component.md`](rules/new-component.md) | Creating an application, package, service, or peer module, especially in a workspace or monorepo. |
| Code and contracts | [`single-author-style.md`](rules/single-author-style.md) | Making implementation changes that should follow the owning project's established sibling patterns. |
| Code and contracts | [`export-boundaries.md`](rules/export-boundaries.md) | Changing a published package, public module, or interface consumed outside its owning project. |
| Code and contracts | [`typescript-first.md`](rules/typescript-first.md) | Working in a TypeScript-capable application or package. Keep it scoped to those projects in a polyglot repository. |
| Testing and diagnostics | [`deterministic-testing.md`](rules/deterministic-testing.md) | Adding or changing tests, fixtures, or test-related verification. |
| Testing and diagnostics | [`diagnostics-and-error-handling.md`](rules/diagnostics-and-error-handling.md) | Resolving type, schema, lint, input-validation, or runtime-error problems. |
| Configuration and tooling | [`demand-driven-configuration.md`](rules/demand-driven-configuration.md) | Adding or changing tool, build, editor, or workflow configuration and its file patterns. |
| Configuration and tooling | [`dependency-security.md`](rules/dependency-security.md) | Adding, updating, moving, or removing packages and their lockfile entries. |
| Configuration and tooling | [`toolchain-and-runtime.md`](rules/toolchain-and-runtime.md) | Changing hooks, CI, scripts, runners, or code that depends on platform and runtime behavior. |
| Compliance and assurance | [`compliance-audit-scope-and-standards.md`](rules/compliance-audit-scope-and-standards.md) | Defining scope and standard editions for an internal compliance audit, readiness review, or gap assessment. |
| Compliance and assurance | [`compliance-audit-evidence.md`](rules/compliance-audit-evidence.md) | Collecting and evaluating evidence for framework requirements or technical controls. |
| Compliance and assurance | [`compliance-audit-findings-and-reporting.md`](rules/compliance-audit-findings-and-reporting.md) | Classifying findings and writing an evidence-backed audit report. |
| Compliance and assurance | [`compliance-audit-remediation.md`](rules/compliance-audit-remediation.md) | Recommending, approving, and re-verifying remediation from audit findings. |
| Compliance and assurance | [`iso-management-system-audits.md`](rules/iso-management-system-audits.md) | Reviewing scope and evidence for ISO management-system standards and related guidance; pair with the general audit rules. |
| Compliance and assurance | [`pci-dss-audits.md`](rules/pci-dss-audits.md) | Establishing CDE scope and reviewing PCI DSS controls; pair with the general audit rules. |

The rules are independent documents. Select them by scope and need; adopting one does not require adopting neighboring rules.

## Adapt rules to your repository

The files in `rules/` are plain Markdown guidance. They intentionally do not contain tool-specific frontmatter or assumptions about a particular repository's commands.

- **Use project facts, not placeholders.** Replace generic references such as “the affected project” with the relevant package, tool, command, or boundary when your agent needs that detail.
- **Keep the scope accurate.** Put repository-wide guidance at the repository level. Put package- or directory-specific guidance in a nested or path-scoped location when your tool supports it.
- **Translate metadata.** Scoping syntax differs between tools. For example, Claude Code uses `paths:`, GitHub Copilot instructions use `applyTo`, and Cursor project rules use `.mdc` metadata such as `globs`. A rule copied from one tool's format may not work unchanged in another.
- **Resolve conflicts before adopting.** Compare the rule with current project instructions, contracts, and established practice. Edit it so the combined instructions are consistent; do not assume every tool applies the same precedence order.
- **Keep always-loaded context focused.** Put broad, durable conventions in instructions that load for most tasks. Use path-scoped rules or task-specific mechanisms supported by your tool for guidance that applies only in one area or workflow.
- **Verify behavior.** Confirm the tool actually discovers the destination file. Then observe whether the guidance helps on a relevant task. If a requirement needs deterministic enforcement, implement that enforcement separately.

For monorepos, apply package-specific rules only to the packages that meet their prerequisites. Keep root-level guidance for genuinely shared tooling, contracts, and workspace behavior. See [Contributing](CONTRIBUTING.md) when proposing changes to this library.

### Example: scope a rule to Cursor API files

Cursor project rules require `.mdc` files with frontmatter; the plain `.md` files in this library are not loaded as Cursor project rules as-is. If your TypeScript API code lives under `apps/api/`, create `.cursor/rules/api-typescript.mdc` with the following frontmatter, then add an adapted copy of the content from [`typescript-first.md`](rules/typescript-first.md):

```md
---
description: Apply TypeScript guidance to API source files
globs: "apps/api/**/*.ts, apps/api/**/*.tsx"
alwaysApply: false
---

<!-- Add the adapted rule content below this line. -->
```

Replace the example paths with your repository's actual paths. The rule attaches when matching files are in context. Check the active rules shown in Cursor, test a task that reads or edits a matching file, and check a non-matching file to confirm the rule stays scoped. See [Cursor's rules documentation](https://cursor.com/docs/rules) for current `.mdc` behavior.

## Connect rules to your coding tool

The following are common project-level instruction locations, not a complete compatibility guarantee. Support can vary by product, editor, version, and settings. Follow the linked documentation before choosing a destination.

| Coding tool | Common project instruction locations | Documentation |
| --- | --- | --- |
| Codex | `AGENTS.md` and configured project instruction files | [AGENTS.md instructions](https://developers.openai.com/codex/guides/agents-md) |
| Claude Code | `CLAUDE.md`, `.claude/CLAUDE.md`, and `.claude/rules/`; `AGENTS.md` support depends on project settings | [Memory and project rules](https://code.claude.com/docs/en/memory) |
| Cursor | `.cursor/rules/*.mdc`; root `AGENTS.md` is also supported in documented use cases | [Rules for AI](https://cursor.com/docs/rules) |
| GitHub Copilot CLI | `AGENTS.md`, `.github/copilot-instructions.md`, and `.github/instructions/**/*.instructions.md` | [Custom instructions for Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-custom-instructions) |
| Gemini CLI | `GEMINI.md` by default; other names can be configured | [GEMINI.md context files](https://geminicli.com/docs/cli/gemini-md/) |

Some tools support importing other files into their project instructions. Use imports only when the tool documents them, and remember that an imported file may be loaded along with the main instructions. Otherwise, copy the selected rule text into a file the tool discovers.

## Rule library scope

These rules provide reusable engineering guidance. They do not replace repository-specific instructions, security policy, or tool documentation. Review their assumptions before use, especially for language-specific rules and changes that cross application or package boundaries.

The TypeScript-first rule targets TypeScript-capable React, Next.js, Node.js, and NestJS projects. It is not a repository-wide mandate for separately maintained components in other languages.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidance on proposing, reviewing, and validating changes to the rule library.
