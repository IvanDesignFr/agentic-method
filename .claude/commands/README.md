# Commands

Commandes slash organisées par catégorie.

## project-management/
| Commande | Usage |
|----------|-------|
| `/discovery` | Planning complet (Brainstorm → PRD → Architecture → Stories) |
| `/auto-discovery` | Planning complet en mode autonome (RALPH) |

## workflows/
| Commande | Usage |
|----------|-------|
| `/feature #N` | Implementation feature depuis une issue GitHub |
| `/auto-feature #N` | Feature complete en mode autonome (RALPH) |
| `/auto-loop "prompt"` | Boucle autonome jusqu'a completion de la tache |
| `/cancel-ralph` | Arrete le mode RALPH |
| `/resume-ralph` | Reprend une session RALPH interrompue |
| `/quick-fix "desc"` | Fix rapide sans workflow complet |
| `/refactor <file>` | Refactoring cible avec 3 passes de review |
| `/validate` | Checklist post-implementation |
| `/pr-review #N` | Review PR (3 passes : Correctness, Readability, Performance) |
| `/status` | Etat du projet |
| `/docs` | Generation documentation |
| `/changelog` | Generation CHANGELOG |
| `/metrics` | Dashboard metriques projet |
| `/init [template]` | Initialise un nouveau projet avec scaffolding |

## research/
| Commande | Usage |
|----------|-------|
| `/multi-mind` | Debat multi-agents pour valider PRD et code |
