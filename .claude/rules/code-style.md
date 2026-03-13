---
# This rule loads at session start (no path filter = global).
# Add paths to scope it: paths: ["src/**/*.py"]
---

# Code Style Rules

## General

- Write clean, readable code. Prefer clarity over cleverness.
- Keep functions small and focused (single responsibility).
- Use descriptive names: `calculate_total_price` not `calc` or `ctp`.
- Avoid deep nesting. Return early to reduce indentation.
- No dead code. Remove unused imports, variables, and functions.
- Only add comments where the logic is not self-evident.

## Python Specific

- Follow PEP8 conventions.
- Use type hints on all function signatures and return types.
- Prefer `dataclass` or `pydantic.BaseModel` over raw dicts for structured data.
- Use `pathlib.Path` instead of `os.path`.
- Prefer f-strings over `.format()` or `%` formatting.
- Use `enum.Enum` for finite sets of values.

## TypeScript Specific

- Use strict TypeScript (`strict: true` in tsconfig).
- Prefer `interface` over `type` for object shapes.
- Use `const` by default, `let` when reassignment is needed, never `var`.
- Prefer named exports over default exports.

## Error Handling

- Only catch exceptions you can handle meaningfully.
- Never silently swallow exceptions.
- Use custom exception types for domain-specific errors.
- Validate at system boundaries (API input, external data), trust internal code.
