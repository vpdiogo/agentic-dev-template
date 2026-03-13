---
name: implement-task
description: Implement a task following its plan, writing code and tests
allowed-tools: Read, Glob, Grep, Write, Edit, Bash, Agent
argument-hint: "[task number or file path]"
---

# Implement Task

Implement a task following the established plan.

## Input

Task reference: $ARGUMENTS

## Workflow

1. **Read the task**: Load `tasks/<task>.md`
2. **Read the plan**: Load `plans/<task>-plan.md` (if it exists)
3. **Read architecture rules**: Check `architecture/overview.md` and relevant CLAUDE.md rules
4. **Implement step by step**: Follow the plan's implementation steps in order
5. **Write tests**: Create tests for the new functionality
6. **Run validation**: Execute linter and test suite
7. **Update task status**: Change status to `done` in the task file

## Rules

- Follow the plan. If the plan is wrong, update it first.
- Follow existing code patterns in the codebase.
- Write tests alongside implementation, not as an afterthought.
- Run linter and tests before marking the task done.
- Keep commits atomic - one logical change per commit.
- If blocked, document the blocker in the task file rather than guessing.
