---
name: review-code
description: Review recent code changes for bugs, security issues, and architecture violations
allowed-tools: Read, Glob, Grep, Bash
context: fork
agent: code-reviewer
argument-hint: "[branch or commit range]"
---

# Review Code

Review code changes for quality, correctness, and security.

## Input

Scope: $ARGUMENTS (defaults to uncommitted changes)

## Process

1. Determine what changed:
   - If no argument: `git diff` for uncommitted changes
   - If branch name: `git diff main...<branch>`
   - If commit range: `git diff <range>`
2. Read each changed file in full to understand context.
3. Check against project rules (CLAUDE.md, architecture docs).
4. Report findings in structured format.

## Output Format

```
## Review Summary

<Overall assessment>

## Issues

### [BLOCKING] <issue>
File: <path>:<line>
<Description and fix>

### [SUGGESTION] <issue>
File: <path>:<line>
<Description and fix>

## Verdict

APPROVED | CHANGES REQUESTED
```
