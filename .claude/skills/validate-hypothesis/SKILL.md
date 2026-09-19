---
name: validate-hypothesis
description: "Protocole de validation hypotheses — transforme les intuitions et signaux en hypotheses testables, les score, et recommande le niveau de validation avant implementation."
model: opus
context: fork
allowed-tools:
  - Read
  - Grep
  - Glob
  - Write
  - Edit
  - WebSearch
argument-hint: <signal-ou-hypothese-a-valider>
user-invocable: true
knowledge:
  core:
    - .claude/knowledge/validate-hypothesis/signal-scoring.md
    - .claude/knowledge/validate-hypothesis/hypothesis-format.md
    - .claude/knowledge/validate-hypothesis/validation-levels.md
---

# Validate Hypothesis — Protocole de validation pre-implementation

## Contexte a charger

| Contexte | Pattern/Action | Priorite |
|----------|----------------|----------|
| Grille scoring signal | `Read: .claude/knowledge/validate-hypothesis/signal-scoring.md` | Requis |
| Format hypothese | `Read: .claude/knowledge/validate-hypothesis/hypothesis-format.md` | Requis |
| Niveaux de validation | `Read: .claude/knowledge/validate-hypothesis/validation-levels.md` | Requis |
| Research README | `Read: docs/research/README.md` | Requis |
| Framework Mom Test | `Read: .claude/knowledge/mom-test/framework.md` | Si niveau 2 |

---

## Activation

> **Au demarrage :**
> 1. Charger les 3 fichiers knowledge core + README research
> 2. Identifier le mode demande :
>    - **Mode 1 — Log Signal** (defaut) — Capturer et scorer un signal brut
>    - **Mode 2 — Formuler Hypothese** — Transformer un signal en hypothese testable
>    - **Mode 3 — Validation Gate** — Evaluer si une hypothese est prete pour implementation

---

## Mode 1 : Log Signal

### Process

**Etape 1 — Capture** : poser les questions de qualification (source, verbatim, contexte, recurrence, comportement vs opinion)

**Etape 2 — Scoring** : appliquer la grille 4 axes (frequence, intensite, diversite, alignement) → score /20

**Etape 3 — Recommandation** : selon le score (16-20 fort, 11-15 prometteur, 6-10 faible, 1-5 bruit)

**Etape 4 — Sauvegarde** : `docs/research/signals/YYYY-MM-DD-titre-court.md`

---

## Mode 2 : Formuler Hypothese

### Process

**Etape 1** — Identifier le signal source

**Etape 2** — Generer la Design Hypothesis au format "We believe that..."

**Etape 3** — Definir metriques de succes, kill criteria, effort, risque

**Etape 4** — Recommander le niveau de validation (matrice effort x signal)

**Etape 5** — Sauvegarder dans `docs/research/hypotheses/H-XXX-titre-court.md`

---

## Mode 3 : Validation Gate

### Process

**Etape 1** — Charger l'hypothese

**Etape 2** — Interroger (qu'as-tu teste ? resultats ? surprises ? biais ?)

**Etape 3** — Passer la checklist 8 criteres

**Etape 4** — Verdict : GO (8/8) / GO avec reserves (6-7/8) / STOP (< 6/8)

**Etape 5** — Mettre a jour le fichier hypothese

---

## Connexions avec les autres skills

| Situation | Skill suivant |
|-----------|---------------|
| Niveau 2 recommande | → `/mom-test` |
| Hypothese validee (GO) | → `/discovery` |
| Hypothese validee + issue existe | → `/feature #XX` |
| Doute sur la formulation | → `/rodin` |

