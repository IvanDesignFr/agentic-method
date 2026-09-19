<!-- PROJECT-RULES-START -->
# Project Rules

> **Cette section est preservee lors des updates.** Ajoutez vos regles projet ici.

<!-- PROJECT-RULES-END -->

---

# D-EPCT+R Workflow

Workflow de dev structure. Detail complet dans `.claude/knowledge/workflows/depct-reference.md`.

## Commandes disponibles

| Commande | Usage |
|----------|-------|
| `/discovery` | Planning complet (Brainstorm -> PRD -> Archi -> Stories) |
| `/feature #N` | Implementation feature depuis une issue |
| `/auto-loop "prompt"` | Boucle autonome RALPH |
| `/auto-feature #N` | Feature complete en autonome |
| `/quick-fix "desc"` | Fix rapide sans workflow complet |
| `/validate` | Checklist post-implementation (tokens, responsive, clean code) |
| `/pr-review #N` | Review PR (3 passes) |
| `/refactor <file>` | Refactoring cible |
| `/status` | Etat du projet |
| `/docs` | Generation documentation |
| `/changelog` | Generation CHANGELOG |

## Principes

- **KISS / DRY / YAGNI**
- Toujours explorer avant de planifier, planifier avant de coder (sauf fix trivial)
- Ne JAMAIS commit/push sur main — branche dediee + PR
- Ne JAMAIS coder sans avoir compris l'existant
- Preferer la simplicite a la complexite
