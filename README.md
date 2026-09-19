# agentic-method

Méthode de développement agentique structurée — skills, commandes, knowledge bases et templates prêts à copier dans n'importe quel projet Claude Code.

Extraite de [Skipper](https://github.com/IvanDesignFr/Skipper), construite sur des mois d'usage réel.

---

## Intégration dans un nouveau projet

```bash
# Cloner le repo
git clone https://github.com/IvanDesignFr/agentic-method.git

# Copier le .claude/ dans votre projet
cp -r agentic-method/.claude /votre-projet/.claude
```

Ouvrez Claude Code dans votre projet — les commandes `/feature`, `/discovery`, `/validate` et les skills sont immédiatement disponibles.

**Adapter ensuite :**
- `.claude/CLAUDE.md` — ajoutez vos règles projet dans la section `PROJECT-RULES`
- `.claude/templates/project-management/github/` — copiez les ISSUE_TEMPLATE dans `.github/` si vous utilisez GitHub

---

## Structure

```
.claude/
├── CLAUDE.md                        ← règles projet + index des commandes
│
├── skills/                          ← skills invocables via /nom-du-skill
│   ├── project-management/          (pm-prd, pm-stories, github-issue-reader)
│   ├── workflows/                   (architect, api-designer, database-designer,
│   │                                 codebase-explainer, implementation-planner,
│   │                                 code-implementer, code-reviewer, rodin)
│   ├── testing/                     (test-runner, performance-auditor)
│   ├── research/                    (idea-brainstorm, mom-test,
│   │                                 validate-hypothesis, multi-mind)
│   ├── design-system/               (ux-designer, ui-designer,
│   │                                 figma-setup, figma-to-code)
│   └── security/                    (security-auditor, supabase-security)
│
├── commands/                        ← commandes slash /nom
│   ├── project-management/          (/discovery, /auto-discovery)
│   ├── workflows/                   (/feature, /auto-feature, /auto-loop,
│   │                                 /validate, /pr-review, /refactor, ...)
│   └── research/                    (/multi-mind)
│
├── knowledge/                       ← bases de connaissances des skills
│   ├── project-management/          (templates PRD, stories, estimation)
│   ├── workflows/                   (D-EPCT+R, architecture, risk assessment)
│   ├── testing/                     (32 docs : Playwright, TDD, fixtures, ...)
│   ├── research/                    (Mom Test, hypothèses, brainstorming)
│   ├── design-system/               (Figma Code Connect, tokens)
│   └── security/                    (Supabase RLS, OWASP, remediation)
│
└── templates/                       ← templates à copier dans votre projet
    ├── project-management/github/   (ISSUE_TEMPLATE, PULL_REQUEST_TEMPLATE)
    ├── devcontainer/                (devcontainer.json, Dockerfile)
    ├── git-hooks/                   (pre-commit, commit-msg)
    └── github-actions/              (ci.yml, deploy.yml, security.yml, ...)
```

---

## Commandes disponibles

| Commande | Usage |
|----------|-------|
| `/discovery` | Planning complet : Brainstorm → PRD → Architecture → Stories |
| `/feature #N` | Implémente une issue GitHub (Explain → Plan → Code → Test → Review) |
| `/auto-feature #N` | Même chose en mode autonome (RALPH) |
| `/validate` | Checklist post-implémentation |
| `/pr-review #N` | Review PR en 3 passes (Correctness, Readability, Performance) |
| `/refactor <file>` | Refactoring ciblé |
| `/quick-fix "desc"` | Fix rapide sans workflow complet |
| `/multi-mind` | Débat 6 agents IA pour valider une décision |

Liste complète → `.claude/commands/README.md`

---

## Principes

- **Pas de ticket = pas de code** — chaque changement est traçable
- **Explorer → Planifier → Coder** — jamais dans l'autre sens
- **1 branche = 1 PR = 1 ticket** — hygiène git stricte
- **Worktrees pour l'isolation** — jamais de code sur main
- **KISS / DRY / YAGNI** — complexité minimale

---

## Sections détaillées

### `project-management/`
Skills : création de PRD, user stories, lecture d'issues GitHub.
Commandes : `/discovery`, `/auto-discovery`.
Knowledge : templates PRD, stories, grille d'estimation.
Templates : ISSUE_TEMPLATE (bug, feature), PULL_REQUEST_TEMPLATE.

### `workflows/`
Le cœur de la méthode : workflow D-EPCT+R (Discover → Explain → Plan → Code → Test → Review), mode autonome RALPH, architecture, API design, base de données.
Commandes : `/feature`, `/auto-feature`, `/auto-loop`, `/validate`, `/pr-review`, `/refactor`, `/docs`, `/changelog`, `/status`, `/metrics`, `/init`.

### `testing/`
Skills : `test-runner` (Playwright, TDD, ATDD), `performance-auditor` (Lighthouse, bundle size).
Knowledge : 32 documents — patterns fixtures, network mocking, sélecteurs, CI burn-in, risk governance.

### `research/`
Méthodes de validation produit avant d'écrire une ligne de code.
Skills : `mom-test`, `validate-hypothesis`, `multi-mind`, `idea-brainstorm`.
Commande : `/multi-mind`.

### `design-system/`
Skills : `ux-designer`, `ui-designer`, `figma-setup`, `figma-to-code`.
Knowledge : guides Figma Code Connect, MCP tools, tokens mapping.

### `security/`
Skills : `security-auditor` (OWASP Top 10, secrets, dépendances), `supabase-security` (RLS, auth, buckets, edge functions).

### `templates/`
Fichiers prêts à copier : devcontainer, git hooks, GitHub Actions (CI, deploy, release, security, Dependabot), templates issues/PR GitHub.

---

Extrait de [Skipper](https://github.com/IvanDesignFr/Skipper) · MIT License
