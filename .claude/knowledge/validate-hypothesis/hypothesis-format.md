# Design Hypothesis — Format standardise

> Transformer un signal qualifie en hypothese testable.

## Format canonique

```
We believe that  [ACTION / CHANGEMENT]
will             [RESULTAT MESURABLE]
for              [PERSONA / SEGMENT]
because          [EVIDENCE / SIGNAL qui motive cette croyance]
```

### Champs obligatoires

| Champ | Description | Bon exemple | Mauvais exemple |
|-------|-------------|-------------|-----------------|
| **Action** | Ce qu'on ferait concretement | "Ajouter une etape d'onboarding guidee" | "Ameliorer l'UX" (trop vague) |
| **Resultat** | Metrique observable et mesurable | "Augmenter le taux d'activation de 30% a 70% a J+7" | "Rendre les gens contents" (pas mesurable) |
| **Persona** | Qui exactement | "Nouveaux utilisateurs B2C inscrits depuis moins d'un mois" | "Les gens" (trop large) |
| **Evidence** | Donnees comportementales reelles | "3/5 interviewes ont abandonne dans les 5 min sans aide" | "On pense que c'est mieux" (opinion) |

### Champs additionnels

| Champ | Description |
|-------|-------------|
| **Metrique de succes** | KPI principal + seuil de validation |
| **Kill criteria** | A quel resultat on abandonne |
| **Effort estime** | S (< 1 jour) / M (1-3 jours) / L (> 3 jours) |
| **Risque principal** | Le plus gros risque si on se trompe |

---

## Statuts d'une hypothese

| Statut | Signification | Prochaine action |
|--------|---------------|------------------|
| **DRAFT** | Formulee, pas encore testee | Determiner le niveau de validation |
| **EN_TEST** | Validation en cours | Completer le niveau, puis Validation Gate |
| **VALIDEE** | Confiance suffisante pour implementer | → `/discovery` ou `/feature` |
| **INVALIDEE** | Les donnees contredisent l'hypothese | Archiver, documenter les learnings |
| **TUEE** | Abandonnee (kill criteria atteint) | Archiver, documenter pourquoi |
| **PIVOTEE** | Reformulee suite aux resultats | Nouvelle hypothese, reference l'ancienne |

---

## Matrice niveau requis vs effort

| Effort estime | Niveau minimum requis | Rationale |
|---------------|----------------------|-----------|
| **S** (< 1 jour) | Niveau 1-2 | Cheap to build → desk research + conversation suffisent |
| **M** (1-3 jours) | Niveau 3 | Investment notable → prototype ou test comportemental |
| **L** (> 3 jours) | Niveau 4-5 | Couteux → fake door ou MVP minimal obligatoire |
