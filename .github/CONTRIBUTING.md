# Contributing

This repository contains reusable, static Markdown guidance for developers to adapt to their coding-agent tools and repositories. It does not contain executable skills or tool plugins.

When proposing a change:

- Keep each document focused on a clear, reusable engineering concern.
- Write guidance in plain Markdown that works across models and coding tools where possible. Mark tool-specific paths, metadata, or behavior explicitly.
- State important scope and assumptions. Avoid presenting repository-specific conventions as universal rules.
- Make examples accurate, minimal, and safe to copy. Link to authoritative sources when guidance depends on tool behavior or changing facts.
- Check neighboring documents and the README for overlap, conflicts, or catalog changes.
- Do not add metadata that a consumer tool will not recognize without explaining how to adapt it.

Before opening a pull request, run `git diff --check` and describe the change, its intended audience, and any sources or checks used. The **Validate Docs** workflow also checks changed lines for whitespace errors.

See the [README](../README.md) for the document catalog and adoption guidance.
