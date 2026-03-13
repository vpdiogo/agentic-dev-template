# Code Review Guidelines

<!-- This file is used by Claude Code Review (GitHub integration). -->
<!-- It is NOT loaded in interactive sessions - use CLAUDE.md for that. -->

## Review Focus Areas

- Correctness: Does the code do what it claims?
- Security: Are there injection risks, exposed secrets, or unsafe operations?
- Architecture: Does the change respect the project's architectural boundaries?
- Tests: Are critical paths covered? Are tests meaningful (not just for coverage)?
- Naming: Are names clear and consistent with existing conventions?

## What to Skip

- Generated files (migrations, lock files, compiled output)
- Formatting-only changes (handled by linter)
- Dependency version bumps (handled by automated tools)

## Review Style

- Be direct and specific. Point to the exact line.
- Suggest fixes, don't just flag problems.
- Distinguish between blocking issues and suggestions.
- Respect existing patterns unless there's a clear reason to change.
