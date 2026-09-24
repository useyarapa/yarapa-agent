# Yarapa Agent Docs

Yarapa Agent Docs is a library of reusable Markdown guidance for developers working with coding agents. Browse `rules/`, select guidance that fits your repository, and add it through the project-instruction format supported by your coding tool.

## Use These Documents with Your Agent

The rule content is model-agnostic, but file discovery and metadata are specific to each coding tool. A local copy does not enter an agent's context until the tool reads it.

### Common project instruction files

| Tool | Project instruction examples |
| --- | --- |
| Codex | `AGENTS.md` |
| Claude Code | `CLAUDE.md`, `AGENTS.md`, `.claude/rules/` |
| Cursor | `AGENTS.md`, `.cursor/rules/` |
| GitHub Copilot CLI | `AGENTS.md`, `.github/copilot-instructions.md`, `.github/instructions/` |
| Gemini CLI | `GEMINI.md` |

File names and supported formats vary by tool. See the official [Codex](https://learn.chatgpt.com/docs/agent-configuration/agents-md), [Claude Code](https://code.claude.com/docs/en/memory), [Cursor](https://cursor.com/docs/rules), [GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-custom-instructions), and [Gemini CLI](https://geminicli.com/docs/cli/tutorials/memory-management/) documentation for current locations and behavior. For example, Claude Code's use of `AGENTS.md` depends on its project-instruction settings and whether `CLAUDE.md` files are present.

### Adoption practices

1. Choose only rules that fit the target repository. Review their assumptions and resolve conflicts with the repository's existing guidance.
2. Copy selected guidance into a project instruction file the tool reads, or reference the source file using a documented import mechanism. Do not assume an arbitrary link or file location will be loaded.
3. Keep always-loaded instructions concise, specific, and actionable. Split distinct concerns into focused files and load detailed guidance only where relevant.
4. Translate or remove metadata such as `paths:` when adapting a rule. Scope syntax differs: Claude Code uses `paths:`, GitHub Copilot uses `applyTo`, and Cursor project rules use `.mdc` metadata such as `globs`. Do not assume frontmatter transfers unchanged.
5. Keep adopted rules in version control and review them as the repository changes. Treat text instructions as guidance; use permissions, hooks, or CI checks for requirements that need deterministic enforcement.

## Available Rules

The rules cover different parts of a codebase. Check each file's `paths:` metadata and assumptions before adopting it; some rules target specific languages, tools, or package layouts.

| Rule | Focus |
| --- | --- |
| [`current-state-authority.md`](rules/current-state-authority.md) | Base implementation decisions on current requirements, tests, contracts, and working-tree state. |
| [`dependency-security.md`](rules/dependency-security.md) | Review dependency maintenance, lifecycle scripts, versions, and lockfile changes. |
| [`deterministic-testing.md`](rules/deterministic-testing.md) | Design focused, deterministic tests for distinct, observable contracts and defects. |
| [`export-boundaries.md`](rules/export-boundaries.md) | Keep package exports explicit and internal modules encapsulated. |
| [`no-anti-patterns.md`](rules/no-anti-patterns.md) | Keep hooks, CI, scripts, and tool execution consistent and predictable. |
| [`no-speculative-config.md`](rules/no-speculative-config.md) | Add configuration for current requirements; avoid unused options and duplicated patterns. |
| [`no-suppression.md`](rules/no-suppression.md) | Resolve type and lint issues at their source while preserving useful error diagnostics. |
| [`single-author-style.md`](rules/single-author-style.md) | Follow established local patterns for structure, naming, types, and abstractions. |
