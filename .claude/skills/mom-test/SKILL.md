---
name: mom-test
description: "Challenge les hypotheses produit avec la methode Mom Test (Rob Fitzpatrick). Detecte les biais, transforme les mauvaises questions en bonnes, et prepare les interviews terrain. Utiliser quand on veut valider une hypothese, preparer une interview utilisateur, ou analyser du feedback."
model: opus
context: fork
allowed-tools:
  - Read
  - Grep
  - Glob
  - Write
  - WebSearch
argument-hint: <hypothese-ou-feature-a-challenger>
user-invocable: true
knowledge:
  core:
    - .claude/knowledge/mom-test/framework.md
---

# Mom Test — Challenge Hypotheses Produit

## Contexte a charger

| Contexte | Pattern/Action | Priorite |
|----------|----------------|----------|
| Framework Mom Test | `Read: .claude/knowledge/mom-test/framework.md` | Requis |
| Research README | `Read: docs/research/README.md` | Requis |
| Interview notes precedentes | `Glob: docs/research/interviews/*.md` | Optionnel |
| Guides existants | `Glob: docs/research/guides/*.md` | Optionnel |

---

## Activation

> **Au demarrage :**
> 1. Charger le framework Mom Test (knowledge core)
> 2. Charger le README research pour connaitre l'etat des hypotheses
> 3. Identifier le mode demande par l'utilisateur :
>    - **Mode Challenge** (defaut) — L'utilisateur presente une hypothese/feature, on la passe au crible Mom Test
>    - **Mode Prep Interview** — Preparer un guide d'interview terrain
>    - **Mode Analyse** — Analyser des notes d'interview existantes
> 4. Demander a l'utilisateur ce qu'il veut challenger ou preparer

---

## Mode 1 : Challenge d'hypotheses

### Process

**Etape 1 — Extraction des hypotheses cachees**

Quand l'utilisateur presente une feature ou decision :

1. **Reformuler** ce qu'il propose
2. **Extraire les hypotheses implicites** :
   - Hypothese de probleme : "Les gens ont CE probleme"
   - Hypothese de solution : "NOTRE solution est la bonne reponse"
   - Hypothese de marche : "Assez de gens paieront pour ca"
   - Hypothese de comportement : "Les gens changeront leurs habitudes pour ca"

3. **Classifier chaque hypothese** :
   - VALIDEE — donnees comportementales reelles
   - NON TESTEE — on croit que c'est vrai mais aucune preuve
   - CONTREDITE — des signaux indiquent le contraire

**Etape 2 — Test Mom Test**

Pour chaque hypothese non testee, transformer les mauvaises questions en bonnes :

| Mauvaise question | Bonne question Mom Test |
|-------------------|------------------------|
| "Tu utiliserais un outil 3D pour la voile ?" | "Comment tu revises entre tes cours ? T'as cherche des trucs ?" |
| "Tu paierais pour ca ?" | "T'as deja paye pour un outil d'apprentissage ? Lequel ? Pourquoi ?" |
| "C'est une bonne idee non ?" | "La derniere fois que t'as ete perdu avec un terme sur le bateau, c'etait quoi ?" |

**Etape 3 — Verdict**

- **VALIDABLE** — On peut tester ca sur le terrain. Voici comment.
- **INVALIDABLE** — L'hypothese est trop vague pour etre testee. La reformuler.
- **DEJA CONTREDITE** — Des signaux existent deja qui fragilisent cette hypothese.
- **VANITY METRIC** — L'hypothese repose sur des opinions, pas des comportements.

### Detection de biais

| Biais | Signal | Reponse |
|-------|--------|---------|
| **Compliment bias** | "Les gens m'ont dit que c'etait genial" | "Qu'est-ce qu'ils ont FAIT ensuite ? Ils y sont retournes ?" |
| **Leading question** | "Tu trouves pas que c'est mieux de..." | "Tu viens de pitcher, pas de questionner. Reformule." |
| **Future promise** | "Ils ont dit qu'ils utiliseraient" | "Les promesses futures ne valent rien. Que font-ils AUJOURD'HUI ?" |
| **Fondateur-centric** | "Moi j'aurais eu besoin de ca quand j'ai debute" | "Tu n'es pas ton utilisateur. Combien de debutants hors de ton cercle ont ce probleme ?" |

---

## Mode 2 : Preparation d'interview terrain

### Process

1. L'utilisateur presente le segment cible et les hypotheses
2. Verifier si un guide existe deja dans `docs/research/guides/`
3. Si oui → le charger et l'adapter
4. Si non → generer un guide au format standard
5. Sauvegarder dans `docs/research/guides/`

STOP — Validation du guide avant d'aller sur le terrain

---

## Mode 3 : Analyse de feedback existant

### Process

1. L'utilisateur fournit des notes ou retours
2. Passer chaque retour au filtre Mom Test :
   - Est-ce un **comportement** ou une **opinion** ?
   - Est-ce **specifique** ou **generique** ?
   - Y a-t-il un **engagement** concret ou juste des mots ?
3. Trier en 3 categories :
   - **Signal fort** — comportement reel + engagement concret
   - **Bruit** — opinion polie, promesse future, compliment
   - **A creuser** — interessant mais pas assez specifique
4. Mettre a jour `docs/research/README.md` avec les nouveaux signaux

---

## Output attendu

Toujours terminer par :

### Scorecard Hypothese

| Hypothese | Statut | Confiance | Action |
|-----------|--------|-----------|--------|
| [H1] | VALIDEE/NON TESTEE/CONTREDITE | Haute/Moyenne/Basse | Valider / Tester / Pivoter |

### Prochaine etape recommandee
- Si hypotheses non testees → Mode Prep Interview
- Si donnees suffisantes → Decision Go/No-Go avec justification
- Si inconclusif → Quelles questions specifiques poser ensuite

