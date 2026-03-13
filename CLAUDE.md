# Project Instructions

<!-- This file is loaded automatically by Claude Code at every session start. -->
<!-- Keep it under 200 lines for best adherence. Use .claude/rules/ for topic-specific instructions. -->
<!-- Use @path/to/file syntax to import additional instruction files. -->

## Project Overview

<!-- Describe your project in 2-3 sentences. -->
<!-- Example: -->
<!-- Backend service for legal document search. Provides REST API for full-text search across legal databases. -->

## Stack

<!-- List your technology stack. -->
<!-- Example: -->
<!-- - Python 3.12 -->
<!-- - FastAPI -->
<!-- - PostgreSQL -->
<!-- - OpenSearch -->

## Architecture

<!-- Describe your architecture briefly. Link to detailed docs. -->
<!-- See @architecture/overview.md for detailed architecture documentation. -->

## Build & Run

<!-- Commands that Claude needs to know. Be explicit. -->
<!-- Example: -->
<!-- ```sh -->
<!-- # Install dependencies -->
<!-- pip install -r requirements.txt -->
<!-- # Run tests -->
<!-- pytest -->
<!-- # Run linter -->
<!-- ruff check . -->
<!-- # Start dev server -->
<!-- uvicorn app.main:app --reload -->
<!-- ``` -->

## Coding Standards

<!-- Be specific and concise. These are enforced by Claude. -->
<!-- Example: -->
<!-- - Follow PEP8, max line length 88 (ruff default) -->
<!-- - Use type hints on all function signatures -->
<!-- - Prefer dependency injection over global state -->
<!-- - Write docstrings only for public APIs -->

## Testing

<!-- Testing conventions. -->
<!-- Example: -->
<!-- - Use pytest with fixtures -->
<!-- - Mock external services, never call real APIs in tests -->
<!-- - Aim for unit tests; integration tests go in tests/integration/ -->

## Git Conventions

<!-- Example: -->
<!-- - Use Conventional Commits: feat|fix|refactor|test|docs|chore(scope): message -->
<!-- - Keep commits atomic and focused -->
<!-- - Write commit messages in English -->

## Important Rules

<!-- Non-negotiable constraints. -->
<!-- Example: -->
<!-- - Never modify migration files after they are committed -->
<!-- - Never commit secrets, .env files, or credentials -->
<!-- - Domain layer must not depend on infrastructure layer -->

## Workflow

When implementing features, follow this workflow:

1. Read the task from `tasks/`
2. Create a plan in `plans/` (or use `/create-plan`)
3. Implement following the architecture rules
4. Write tests
5. Run linter and tests before committing

## Additional Context

<!-- Import modular rules as needed: -->
<!-- @.claude/rules/code-style.md -->
<!-- @.claude/rules/testing.md -->
<!-- @.claude/rules/api-design.md -->
<!-- @architecture/overview.md -->
<!-- @decisions/ -->
