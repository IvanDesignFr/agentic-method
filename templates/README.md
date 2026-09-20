# templates

Ready-to-copy starters for new projects.

## Contents

## Contents

| Path | Description |
|------|-------------|
| `devcontainer/devcontainer.json` | Dev container configuration |
| `devcontainer/Dockerfile` | Base Docker image |
| `devcontainer/docker-compose.yml` | Docker Compose for dev environment |
| `git-hooks/pre-commit` | Pre-commit hook (lint, format checks) |
| `git-hooks/commit-msg` | Commit message format validation |
| `github-actions/ci.yml` | CI workflow (tests, lint) |
| `github-actions/deploy.yml` | Deployment workflow |
| `github-actions/release.yml` | Release workflow |
| `github-actions/security.yml` | Security scanning workflow |
| `github-actions/dependabot.yml` | Dependabot configuration |

## Quick start

Copy the relevant templates to your project:
- `devcontainer/` → `.devcontainer/`
- `git-hooks/` → `.git/hooks/` (make executable with `chmod +x`)
- `github-actions/` → `.github/workflows/`
