# Repository Guidelines

## Project Structure & Module Organization

This is a documentation-only repository; it has no application source, runtime package, assets, or test directory.

- `rules/` contains independently adoptable Markdown guidance.
- `README.md` explains the library, helps users choose and adapt rules, and links to tool documentation.
- `CONTRIBUTING.md` defines documentation authoring expectations.
- `.github/` contains issue and pull request templates, the security policy, and the documentation validation workflow.

## Build, Test, and Development Commands

There is no build or local development server. Before submitting documentation changes, run:

- `git diff --check` — find whitespace errors in working-tree changes.
- `git diff --check origin/main...HEAD` — check committed changes against the PR base; replace `origin/main` if the PR targets another branch.

The **Validate Docs** GitHub Actions workflow also checks changed lines for whitespace errors. It does not validate factual accuracy or links.

## Writing Style & Naming Conventions

Write plain Markdown in a direct, professional tone. Keep each rule focused on one reusable engineering concern, and state its scope and assumptions so users can adapt it safely. Prefer descriptive `kebab-case.md` filenames, such as `dependency-security.md`. Keep guidance model-agnostic where possible; identify tool-specific file paths, metadata, and behavior. Make examples minimal and safe to copy, and link to authoritative sources for tool behavior that may change. Update the README catalog when adding, renaming, or substantially changing a rule.

## Testing Guidelines

There is no unit or integration test framework and no coverage requirement. Review changed links, filenames, commands, and examples manually. Use `git diff --check` for whitespace validation; the CI workflow checks whitespace only.

## Commit & Pull Request Guidelines

Recent commits use descriptive subjects such as `docs(rules): add git history policy` and `docs: update documentation for clarity`; follow the nearby `docs:` convention and name the area when useful. Submit changes through a pull request—repository policy rejects direct pushes to `main`. Complete `.github/pull_request_template.md`: summarize the outcome, list changed documents and their audience, and record sources and validation. Check the template checklist before requesting review.
