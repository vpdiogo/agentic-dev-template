# Agentic Development Template

Template repository for AI-assisted software development with [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

This template structures your repository as an **AI-native codebase** — where agents, tasks, plans, and architectural context are versioned alongside your code.

## Quick Start

1. Click **"Use this template"** on GitHub to create a new repository
2. Customize `CLAUDE.md` with your project's stack, architecture, and rules
3. Fill in `architecture/overview.md` with your architecture details
4. Start working: create tasks, generate plans, implement features

## Repository Structure

```
.
├── CLAUDE.md                          # Main project instructions (loaded every session)
├── REVIEW.md                          # Code review guidelines (GitHub integration)
├── .gitignore
│
├── .claude/
│   ├── settings.json                  # Team-shared permissions and hooks
│   │
│   ├── rules/                         # Modular instructions by topic
│   │   ├── code-style.md             # Coding standards
│   │   ├── testing.md                # Testing conventions (scoped to test files)
│   │   └── api-design.md            # API design rules (scoped to route files)
│   │
│   ├── agents/                        # Custom subagents with specialized roles
│   │   ├── planner.md                # Creates implementation plans from tasks
│   │   ├── code-reviewer.md          # Reviews changes for quality and security
│   │   ├── researcher.md             # Read-only codebase exploration
│   │   └── tester.md                 # Generates tests for existing code
│   │
│   └── skills/                        # Custom slash commands
│       ├── create-task/SKILL.md      # /create-task — scaffolds a task file
│       ├── create-plan/SKILL.md      # /create-plan — generates implementation plan
│       ├── implement-task/SKILL.md   # /implement-task — executes a task
│       └── review-code/SKILL.md      # /review-code — reviews recent changes
│
├── tasks/                             # Task definitions (unit of work)
│   └── 001-example-feature.md
│
├── plans/                             # Implementation plans (generated from tasks)
│
├── specs/                             # Feature specifications (input for tasks)
│   └── example-spec.md
│
├── architecture/                      # Architecture documentation
│   └── overview.md
│
└── decisions/                         # Architecture Decision Records (ADRs)
    └── 000-template.md
```

## How It Works

### The Development Workflow

```
Spec → Task → Plan → Implement → Test → Review → Commit
```

1. **Spec** (`specs/`): Define WHAT the system should do
2. **Task** (`tasks/`): Define a unit of work with acceptance criteria
3. **Plan** (`plans/`): Break the task into implementation steps
4. **Implement**: Write code following the plan and architecture rules
5. **Test**: Write and run tests
6. **Review**: Check for bugs, security issues, architecture violations
7. **Commit**: Atomic commit with conventional message

### Using Slash Commands

| Command | Description |
|---------|-------------|
| `/create-task <title>` | Create a new task file with structured template |
| `/create-plan <task>` | Analyze a task and generate an implementation plan |
| `/implement-task <task>` | Implement a task following its plan |
| `/review-code [scope]` | Review code changes for quality and correctness |

### Using Agents

Claude Code automatically delegates to specialized agents when appropriate:

- **Planner**: Analyzes tasks and creates step-by-step plans
- **Code Reviewer**: Reviews changes for bugs, security, and architecture violations
- **Researcher**: Explores the codebase to answer questions (read-only)
- **Tester**: Generates meaningful tests for existing code

### Context Hierarchy

```
CLAUDE.md                    → Always loaded (project rules)
.claude/rules/*.md           → Loaded by topic/path scope
architecture/overview.md     → Referenced by agents for design decisions
decisions/*.md               → Referenced for architectural context
tasks/*.md                   → Input for implementation workflow
```

## Customization Guide

### 1. Configure CLAUDE.md

This is the most important file. Fill in:
- Your tech stack
- Architecture description
- Build/test/lint commands
- Coding standards
- Non-negotiable rules

### 2. Set Up Architecture Docs

Edit `architecture/overview.md` with:
- Your architecture style (hexagonal, layered, clean, etc.)
- Directory structure
- Dependency rules between layers
- Data flow description

### 3. Adjust Rules

Edit files in `.claude/rules/` to match your conventions:
- `code-style.md` — language-specific coding standards
- `testing.md` — test framework and conventions
- `api-design.md` — API patterns (or remove if not applicable)

Add new rule files for your needs (e.g., `database.md`, `security.md`).

### 4. Configure Permissions

Edit `.claude/settings.json` to allow/deny specific tool usage for your stack.

### 5. Record Decisions

Copy `decisions/000-template.md` to create ADRs for important technical decisions.

## Key Concepts

### Why CLAUDE.md?

Claude Code loads `CLAUDE.md` at every session start. It acts as persistent project context — your stack, rules, and conventions. This dramatically improves code consistency.

### Why Tasks?

Tasks are atomic units of work with clear acceptance criteria. They give Claude a focused scope instead of vague instructions, resulting in better implementations.

### Why Plans?

Plans prevent Claude from jumping straight to code. Analyzing the task, exploring the codebase, and creating a step-by-step plan produces more thoughtful, architecture-aligned implementations.

### Why Rules?

Rules in `.claude/rules/` are modular and path-scoped. Testing rules only load when working on test files. API rules only load when working on route files. This keeps context focused and efficient.

## Tips

- Keep `CLAUDE.md` under 200 lines. Use `@path/to/file` imports for details.
- Write tasks with clear acceptance criteria. Vague tasks produce vague code.
- Create plans before implementing complex features.
- Use ADRs to document why you chose a technology or pattern.
- Specs describe WHAT, tasks describe WHAT TO DO, plans describe HOW.
- Run `/review-code` before committing to catch issues early.

## License

MIT
