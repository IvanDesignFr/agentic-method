# agentic-method

A reusable agentic development methodology for AI-assisted software projects.

Built from real-world usage on [Skipper](https://github.com/IvanDesignFr/Skipper) — a sailing simulator. Extracted to be dropped into any project.

## What is this?

A structured set of skills, workflows, commands, and templates that turn Claude Code (or any Claude-powered agent) into a disciplined engineering collaborator — one that plans before coding, traces decisions, and never ships without a ticket.

## Structure

```
agentic-method/
├── project-management/   # Tickets, PRD, stories, GitHub conventions
├── workflows/            # D-EPCT+R, feature lifecycle, commands
├── testing/              # Test strategies, runners, coverage gates
├── research/             # Mom Test, hypothesis validation, interviews
├── design-system/        # UI/UX skills, Figma integration, tokens
├── security/             # Security audits, Supabase, OWASP checklists
└── templates/            # CLAUDE.md starters, hooks, GitHub templates
```

## How to use in a new project

1. Copy the relevant sections into your project's `.claude/` directory
2. Adapt `templates/CLAUDE.md` to your project conventions
3. Set up your GitHub labels and milestones matching `project-management/`
4. Start with `/discovery` or `/feature #N`

## Core principles

- **No ticket = no code** — every change is traceable
- **Explore → Plan → Code → Test → Review** — never skip steps
- **KISS / DRY / YAGNI** — minimum complexity for current needs
- **One branch, one PR, one ticket** — clean git hygiene
- **Worktrees for isolation** — never code on main

## Sections

### `project-management/`
GitHub issue conventions, milestone structure, epic labels, sizing grid, decision log format.

### `workflows/`
The D-EPCT+R loop (Discover, Explain, Plan, Code, Test, Review), slash commands, RALPH autonomous mode.

### `testing/`
Test strategies, Cypress patterns, coverage requirements, pre-merge checklists.

### `research/`
Mom Test method, hypothesis validation protocol, user interview templates.

### `design-system/`
Design token conventions, Figma Code Connect setup, UI/UX skill prompts.

### `security/`
Supabase RLS audits, OWASP checklist, secrets detection, dependency scanning.

### `templates/`
Ready-to-copy CLAUDE.md starters, git hooks, GitHub Actions, issue templates.

---

Extracted from [Skipper](https://github.com/IvanDesignFr/Skipper) · MIT License
