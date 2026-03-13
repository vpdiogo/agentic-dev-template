---
name: create-plan
description: Create an implementation plan for a task before coding
allowed-tools: Read, Glob, Grep, Write
context: fork
agent: planner
argument-hint: "[task number or file path]"
---

# Create Plan

Analyze the specified task and create a detailed implementation plan.

## Input

Task reference: $ARGUMENTS

## Steps

1. Read the task file from `tasks/`.
2. Read relevant architecture docs from `architecture/`.
3. Explore the codebase to understand existing patterns.
4. Create a plan file at `plans/<task-id>-plan.md`.

## Plan Structure

```markdown
# Plan: <task title>

Task: tasks/<NNN>-<slug>.md
Created: <date>

## Analysis

<What needs to change and why>

## Impacted Areas

- <module/file>: <what changes>

## Implementation Steps

1. <Step>: <description>
   - Files: <affected files>
   - Dependencies: <step dependencies>
2. <Step>: <description>
   ...

## Testing Strategy

- <What to test>
- <How to test>

## Risks & Considerations

- <Potential issue and mitigation>
```
