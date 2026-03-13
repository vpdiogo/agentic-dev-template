---
name: create-task
description: Create a new task file in the tasks/ directory with structured format
allowed-tools: Read, Glob, Write
argument-hint: "[task title]"
---

# Create Task

Create a new task file in the `tasks/` directory.

## Steps

1. List existing files in `tasks/` to determine the next task number.
2. Create a new file: `tasks/<NNN>-<slugified-title>.md`
3. Use the template below, filling in details from `$ARGUMENTS` or asking the user.

## Template

```markdown
# Task <NNN>: <Title>

Status: draft
Priority: medium
Created: <date>

## Context

<Why this task exists. What problem it solves.>

## Requirements

- <Requirement 1>
- <Requirement 2>

## Acceptance Criteria

- [ ] <Criterion 1>
- [ ] <Criterion 2>
- [ ] Tests pass
- [ ] No linter errors

## Notes

<Optional: links, references, constraints, related tasks>
```

## Rules

- Number tasks sequentially (001, 002, 003...).
- Use kebab-case for file names.
- Keep task descriptions focused and actionable.
- Default status is `draft`. Change to `in-progress` when work begins.
- Valid statuses: draft, in-progress, done, cancelled.
