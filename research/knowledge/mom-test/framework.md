# The Mom Test — Framework de reference

> Source : "The Mom Test" de Rob Fitzpatrick

## Les 3 regles du Mom Test

### Regle 1 : Parler de leur vie, pas de ton idee
- Les gens vont te mentir pour etre polis → ne leur en donne pas l'occasion
- Au lieu de : "J'ai cette idee de..." → "Comment tu geres [probleme] aujourd'hui ?"
- Si tu mentionnes ton produit, l'interview est foutue

### Regle 2 : Poser des questions sur le passe (specifiques), pas le futur (generiques)
- "Tu utiliserais X ?" → inutile (tout le monde dit oui)
- "Raconte-moi la derniere fois que [probleme] t'est arrive" → comportement reel
- Les comportements passes predisent les comportements futurs. Les opinions ne predisent rien.

### Regle 3 : Parler moins, ecouter plus
- Ratio cible : 20% toi, 80% eux
- Chaque fois que tu parles, tu perds de l'information
- Le silence est ton meilleur outil — laisse-les remplir le vide

---

## Les questions qui marchent

### Questions universelles
1. "Parle-moi de comment tu [activite liee au probleme]"
2. "C'est quoi le plus dur dans [domaine] ?"
3. "Pourquoi c'est dur ?"
4. "Comment tu resous ca aujourd'hui ?"
5. "Qu'est-ce qui ne va pas avec ta solution actuelle ?"
6. "La derniere fois que c'est arrive, qu'est-ce que t'as fait ?"

### Questions de suivi (creuser)
- "Qu'est-ce que tu veux dire par [terme vague] ?"
- "Pourquoi ca t'a derange ?"
- "Et apres, qu'est-ce que t'as fait ?"
- "Tu as essaye de trouver une solution ? Laquelle ?"
- "Combien de temps/argent tu y passes ?"

### Questions d'engagement (valider l'intention)
- "Tu serais pret a essayer un prototype la semaine prochaine ?"
- "Tu connais d'autres personnes qui ont ce probleme ? Tu peux me les presenter ?"
- "Si je te montre quelque chose dans 2 semaines, tu aurais 20 min ?"

---

## Les signaux a detecter

### Signaux forts (le probleme est reel)
- La personne a deja cherche une solution (temps investi)
- La personne paie deja pour resoudre le probleme (argent investi)
- La personne a un workaround bricole (effort investi)
- La personne devient emotionnelle en decrivant le probleme
- La personne pose des questions sur ta solution AVANT que tu en parles

### Signaux faibles (attention, bruit)
- "Ouais, ca pourrait etre utile" (politesse)
- "C'est une super idee !" (compliment ≠ engagement)
- "J'utiliserais ca" (promesse future = sans valeur)
- "Plein de gens auraient besoin de ca" (projection vague)
- "Tu devrais ajouter [feature X]" (feature request sans probleme)

### Signaux d'invalidation
- La personne n'a jamais essaye de resoudre le probleme
- Le probleme existe mais n'est pas assez douloureux pour agir
- La solution actuelle (meme imparfaite) suffit
- Refus de s'engager (pas de temps pour un test, pas d'intro)

---

## Les anti-patterns classiques

### 1. Pitcher au lieu de questionner
- "On construit un outil pour [faire X] et..."
- "Comment tu [fais X] aujourd'hui ?"

### 2. Questions fermees / orientees
- "Tu trouves pas que c'est galere de retenir le vocabulaire ?"
- "Raconte-moi la derniere fois que t'as ete perdu avec un terme sur le bateau."

### 3. Chercher la validation
- "Les gens adorent le modele 3D. Tu le trouves bien aussi ?"
- "Qu'est-ce que t'as fait en premier en arrivant sur le site ?"

### 4. Trop de monde, pas assez de profondeur
- Sondage a 500 personnes avec questions fermees
- 5 conversations approfondies de 20 min avec des vrais debutants

### 5. Confondre donnees et opinions
- "80% des gens disent qu'ils utiliseraient notre outil" (opinion)
- "3 personnes sur 5 avaient cherche le vocabulaire en ligne avant leur cours" (fait)

---

## Framework d'analyse post-interview

### Pour chaque retour, se demander :
1. **C'est un fait ou une opinion ?**
   - Fait = comportement passe observe
   - Opinion = prediction future, jugement de valeur
2. **C'est specifique ou generique ?**
   - Specifique = "avant mon cours samedi, j'ai regarde 3 videos YouTube sur les allures"
   - Generique = "des fois je cherche des infos sur le sujet"
3. **Il y a un engagement ou juste des mots ?**
   - Engagement = temps, argent, reputation investis
   - Mots = "j'adorerais", "c'est top", "plein de gens..."

### Matrice de fiabilite

|                | Specifique | Generique |
|----------------|-----------|-----------|
| **Fait**       | Signal fort | A creuser |
| **Opinion**    | Interessant | Bruit |

---

## Exemples generiques

### Hypothese : "Les utilisateurs veulent [feature X]"

- "Tu utiliserais [feature X] ?"
  → Tout le monde dit oui. Ca ne vaut rien.

- "La derniere fois que t'as eu ce probleme, t'as fait quoi ?"
  → Comportement reel. S'ils n'ont rien fait → le besoin n'existe peut-etre pas.

- "Comment tu resous ce probleme aujourd'hui ?"
  → Anecdote concrete. Douleur mesurable.

### Hypothese : "Les [utilisateurs B2B] recommanderaient l'outil"

- "Vous recommanderiez [produit] a vos [clients/equipes] ?"
  → Bien sur qu'ils disent oui. Ca ne vaut rien.

- "Qu'est-ce que vous envoyez a vos [clients/equipes] aujourd'hui pour resoudre ce probleme ?"
  → Workflow reel. Friction reelle ou non.

- "Vos [clients/equipes] retiennent quoi de leur derniere formation ?"
  → Fait observe. Le probleme existe-t-il vraiment ?
