# workflows

The D-EPCT+R development loop, slash commands, and RALPH autonomous mode.

## The D-EPCT+R Loop

| Step | Description |
|------|-------------|
| **D** — Discover | Read the ticket, explore the codebase |
| **E** — Explain | Understand the impacted code |
| **P** — Plan | Write an implementation plan |
| **C** — Code | Implement, respecting conventions |
| **T** — Test | Write and run tests |
| **R** — Review | 3-pass review (Correctness, Readability, Performance) |

## Contents

## Skills

| Skill | Usage |
|-------|-------|
| `skills/implementation-planner/` | Create a detailed implementation plan from requirements (`/implementation-planner`) |
| `skills/codebase-explainer/` | Analyse source code before planning implementation (`/codebase-explainer`) |
| `skills/code-implementer/` | Implement code following a validated plan (`/code-implementer`) |
| `skills/rodin/` | Socratic interlocutor for deep discussions (`/rodin`) |

## Commands

| Command | Usage |
|---------|-------|
| `commands/feature.md` | Full D-EPCT+R feature workflow from a GitHub issue (`/feature #N`) |
| `commands/auto-feature.md` | Autonomous feature implementation (`/auto-feature #N`) |
| `commands/auto-loop.md` | Autonomous RALPH loop (`/auto-loop "prompt"`) |
| `commands/cancel-ralph.md` | Stop an active RALPH loop (`/cancel-ralph`) |
| `commands/resume-ralph.md` | Resume an interrupted RALPH session (`/resume-ralph`) |
| `commands/quick-fix.md` | Quick fix without full workflow (`/quick-fix "desc"`) |
| `commands/refactor.md` | Targeted refactoring (`/refactor <file>`) |
| `commands/validate.md` | Post-implementation checklist (`/validate`) |
| `commands/status.md` | Project status dashboard (`/status`) |
| `commands/docs.md` | Generate documentation (`/docs`) |
| `commands/changelog.md` | Generate CHANGELOG (`/changelog`) |
| `commands/metrics.md` | Project metrics dashboard (`/metrics`) |
| `commands/init.md` | Scaffold a new project (`/init`) |

## Knowledge

| File | Description |
|------|-------------|
| `knowledge/depct-reference.md` | Full D-EPCT+R workflow reference |
| `knowledge/architecture-template.md` | Architecture document template |
| `knowledge/risk-assessment.md` | Risk assessment framework |
| `knowledge/ux-template.md` | UX design document template |
| `knowledge/ui-template.md` | UI design document template |
