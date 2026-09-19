# D-EPCT+R Workflow — Reference complete

## Architecture

```
PLANNING:   Brainstorm -> [UX] -> PRD -> [UI] -> Architecture -> Stories -> GitHub
DEVELOPPEMENT: Explain -> Plan -> Code (+Lint/Type) -> Test -> Review x3
MODE MANUEL: Validation humaine a chaque etape
MODE RALPH:  Autonome jusqu'a completion promise / max iter / timeout
```

## Commandes (16)

### Mode Manuel
- `/discovery` — Planning complet avec validation a chaque etape
- `/feature [issue]` — Implementation avec validation a chaque etape

### Mode RALPH (autonome)
- `/auto-loop "prompt"` — Boucle generique (max 20 iter, timeout 1h)
- `/auto-discovery "idee"` — Planning autonome (max 30 iter, timeout 1h)
- `/auto-feature #123` — Implementation autonome (max 50 iter, timeout 2h)
- `/cancel-ralph` — Arreter le mode RALPH
- `/resume-ralph [session-id]` — Reprendre une session interrompue

Options RALPH : `--max N`, `--timeout Xh`, `--promise "TEXT"`, `--no-log`, `--verbose`

### Utilitaires
- `/status` — Etat du projet
- `/pr-review #123` — Review PR (3 passes)
- `/quick-fix "desc"` — Fix rapide
- `/validate` — Checklist post-implementation
- `/refactor <file>` — Refactoring cible
- `/docs [type]` — Documentation (readme|api|guide|all)
- `/changelog [version]` — CHANGELOG.md
- `/metrics` — Dashboard metriques
- `/init [template]` — Scaffolding (next|express|api|cli|lib)

## Skills (20)

### Planning
| Skill | Role |
|-------|------|
| `idea-brainstorm` | Exploration creative (61 techniques, anti-biais) |
| `pm-prd` | Product Requirements (FULL/LIGHT) |
| `architect` | Architecture technique |
| `pm-stories` | Epics + Stories (INVEST, Readiness Check /15) |
| `api-designer` | Design d'API (OpenAPI 3.1) |
| `database-designer` | Design de BDD |

### Design (optionnel, auto-triggered)
| Skill | Role |
|-------|------|
| `ux-designer` | Personas, journeys, wireframes |
| `ui-designer` | Tokens, composants UI |
| `figma-setup` | Config Code Connect |
| `figma-to-code` | URL Figma -> code |

### Developpement
| Skill | Role |
|-------|------|
| `github-issue-reader` | Lecture d'issues |
| `codebase-explainer` | Analyse du code |
| `implementation-planner` | Planification (TaskCreate si 2+ etapes) |
| `code-implementer` | Implementation (lint/types par etape) |
| `test-runner` | Tests (ATDD/Standard, P0-P3) |
| `code-reviewer` | Review 3 passes (Correctness -> Readability -> Performance) |
| `security-auditor` | Audit OWASP Top 10 |
| `performance-auditor` | Core Web Vitals, bundle size |
| `supabase-security` | Audit Supabase |
| `multi-mind` | Debat multi-agents (6 IA, 5 rounds) |

## Skill Chaining

brainstorm -> [ux] -> prd -> [ui] -> architect -> stories -> feature
issue-reader -> codebase-explainer -> planner -> implementer -> test-runner -> reviewer -> Commit/PR

### Seuils de validation
| Skill | Seuil |
|-------|-------|
| `idea-brainstorm` | 4/5 |
| `pm-prd` | 6/7 |
| `architect` | 5/6 |
| `pm-stories` | 13/15 |
| `implementation-planner` | 5/6 |
| `code-implementer` | 4/5 |
| `test-runner` | 4/5 |
| `code-reviewer` | Toutes passes OK |

## Modes de scope

**FULL** (score >= 3 : 3+ features, archi multi-composants, 3+ ecrans, integrations externes, > 1 jour) :
Brainstorm -> [UX] -> PRD complet -> [UI] -> Architecture -> Stories -> GitHub

**LIGHT** (feature isolee, < 1 jour) :
PRD simplifie -> Stories -> GitHub

## Plan Mode

Pour les taches non-triviales, utiliser Plan Mode :
1. Explore (agent) -> Recherche dans le codebase
2. EnterPlanMode -> Designer la solution
3. Validation utilisateur
4. Execution avec Tasks pour tracking

## Task System

Utiliser quand 2+ etapes d'implementation. Outils : TaskCreate, TaskList, TaskGet, TaskUpdate.
Multi-sessions : `CLAUDE_CODE_TASK_LIST_ID=mon-projet claude`

## Subagents

| Agent | Usage |
|-------|-------|
| `Explore` | Recherche dans le codebase |
| `Plan` | Conception de plans |

## Checkpoints obligatoires

Planning: Brainstorm valide -> [UX] -> PRD valide -> [UI] -> Architecture validee -> Readiness >= 13/15
Dev: Code explique -> Plan valide -> Code implemente (Lint+Types OK) -> Tests passent -> Review 3 passes OK

## Templates

| Template | Emplacement |
|----------|-------------|
| Git hooks | `.claude/templates/git-hooks/` |
| DevContainer | `.claude/templates/devcontainer/` |
| GitHub Issues | `.claude/templates/github/ISSUE_TEMPLATE/` |
| GitHub Actions | `.claude/templates/github-actions/` |
| PR Template | `.claude/templates/github/PULL_REQUEST_TEMPLATE.md` |

## Knowledge Base

| Dossier | Contenu |
|---------|---------|
| `testing/` | 32 fragments (levels, priorities, fixtures, healing...) |
| `workflows/` | Templates PRD, archi, stories, UX, UI + estimation |
| `brainstorming/` | 61 techniques en 10 categories |
| `multi-mind/` | 6 agents, templates 5 rounds |
| `supabase-security/` | Checklist audit, CVSS, RLS, remediation |
| `figma/` | Code Connect, MCP, tokens mapping |

## Documentation

| Type | Emplacement |
|------|-------------|
| Brainstorms | `docs/planning/brainstorms/` |
| UX Design | `docs/planning/ux/` |
| PRD | `docs/planning/prd/` |
| UI Design | `docs/planning/ui/` |
| Architecture | `docs/planning/architecture/` |
| Stories | `docs/stories/EPIC-{num}-{slug}/` |
| Logs RALPH | `docs/ralph-logs/` |

## Conventions

Commits: `type(scope): description` — Types: feat, fix, refactor, test, docs, chore
Branches: `feature/[issue]-desc` ou `fix/[issue]-desc`
PR: Lier avec "Closes #XX", description claire, screenshots si UI

## Regles globales

### Mode Manuel
- Ne JAMAIS enchainer sans validation explicite
- Attendre "ok"/"continue"/"valide" avant de continuer

### Mode RALPH
- Ne JAMAIS ignorer les erreurs (s'auto-corriger)
- Logger chaque iteration dans `docs/ralph-logs/`
- S'arreter sur : completion promise, max iterations, ou timeout

### Tous modes
- Ne JAMAIS commit/push sur main (branche + PR)
- Ne JAMAIS committer sans tests qui passent
- Ne JAMAIS merger sans les 3 passes de review
