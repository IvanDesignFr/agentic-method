# Niveaux de validation — Framework progressif

> Valider a moindre cout avant d'investir.

## Les 5 niveaux

### Niveau 1 — Desk Research (5-15 min)

**Actions :**
- Google Scholar / recherche web sur le sujet
- Benchmarks concurrents (comment font les autres ?)
- Analytics existantes du produit
- Relire les notes d'interviews passees

**Criteres de passage :**
- Si donnees suffisantes → decision directe (GO ou KILL)
- Si inconclusif mais signal interessant → Niveau 2
- Si aucun signal → KILL ou archiver

---

### Niveau 2 — Conversations Mom Test (30-60 min)

**Actions :**
- 3-5 conversations ciblees (Mom Test)
- Questions sur le passe, pas le futur
- Chercher des comportements, pas des opinions
- Utiliser `/mom-test` pour preparer le guide d'interview

**Criteres de passage :**
- Si 3/5+ confirment un comportement reel → GO ou Niveau 3 si effort L
- Si resultats mitiges (2/5) → 3 interviews de plus ou reformuler
- Si 0-1/5 → KILL

---

### Niveau 3 — Prototype / Test de concept (2-4h)

**Actions :**
- Wireframe ou prototype Figma (pas de code)
- Test avec 3-5 personnes (15 min chacune)
- Observer : comprennent-ils ? Sont-ils interesses ?

**Criteres de passage :**
- Si 3/5+ comprennent ET sont interesses → GO
- Si comprennent mais pas interesses → revoir la proposition de valeur
- Si ne comprennent pas → revoir le concept

---

### Niveau 4 — Fake Door / Wizard of Oz (1 jour)

**Actions :**
- Bouton/CTA qui mesure les clics (la feature n'existe pas encore)
- Landing page avec CTA "s'inscrire" pour mesurer l'interet

**Criteres de passage :**
- Taux de clic > 5% = signal, > 15% = fort
- Si bien en dessous → KILL

---

### Niveau 5 — MVP Minimal (2-5 jours)

**Actions :**
- Implementer la version la plus reduite de la feature
- Mesurer l'usage reel (pas les opinions)
- Periode de mesure : minimum 1-2 semaines

---

## Matrice de decision

| | Signal faible (6-10) | Signal prometteur (11-15) | Signal fort (16-20) |
|---|---|---|---|
| **Effort S** (< 1j) | Niveau 1 puis GO/KILL | Niveau 1 → GO | GO direct |
| **Effort M** (1-3j) | Niveau 2 | Niveau 2-3 | Niveau 1-2 |
| **Effort L** (> 3j) | Niveau 3 minimum | Niveau 3-4 | Niveau 2-3 |

---

## Criteres de KILL

Une hypothese doit etre tuee si :
1. **0 comportement reel** — Personne n'a jamais essaye de resoudre ce probleme
2. **Pas assez douloureux** — Le probleme existe mais les gens vivent avec
3. **Solution actuelle suffisante** — Le workaround existant est "good enough"
4. **Hors vision** — Meme si valide, ca eloigne le produit de sa mission
5. **Kill criteria atteint** — La metrique definie a l'avance n'est pas atteinte
