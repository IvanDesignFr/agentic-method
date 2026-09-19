# Templates

Templates prets a l'emploi pour nouveaux projets.

| Dossier | Contenu |
|---------|---------|
| `devcontainer/` | `devcontainer.json`, `Dockerfile`, `docker-compose.yml` — environnement de dev containerise |
| `git-hooks/` | `pre-commit`, `commit-msg` — hooks Git pour qualite de code |
| `github/` | `ISSUE_TEMPLATE/` (bug report, feature request, config), `PULL_REQUEST_TEMPLATE.md` |
| `github-actions/` | `ci.yml`, `deploy.yml`, `release.yml`, `security.yml`, `dependabot.yml` |

## Usage

Copier le dossier voulu dans votre projet :

```bash
# GitHub templates
cp -r .claude/templates/github/.github .

# Git hooks
cp .claude/templates/git-hooks/pre-commit .git/hooks/
cp .claude/templates/git-hooks/commit-msg .git/hooks/
chmod +x .git/hooks/pre-commit .git/hooks/commit-msg

# Devcontainer
cp -r .claude/templates/devcontainer .devcontainer
```
