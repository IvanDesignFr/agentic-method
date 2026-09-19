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
- "On construit une app pour gerer les projets d'equipe et..."
- "Comment tu organises tes taches actuellement ?"

### 2. Questions fermees / orientees
- "Tu trouves pas que c'est galere de retrouver ses fichiers ?"
- "Raconte-moi la derniere fois que t'as perdu du temps a chercher un document."

### 3. Chercher la validation
- "Les gens adorent notre dashboard. Tu le trouves bien aussi ?"
- "Qu'est-ce que t'as fait en premier en arrivant sur le site ?"

### 4. Trop de monde, pas assez de profondeur
- Sondage a 500 personnes avec questions fermees
- 5 conversations approfondies de 20 min avec de vrais utilisateurs

### 5. Confondre donnees et opinions
- "80% des gens disent qu'ils utiliseraient notre outil" (opinion)
- "3 personnes sur 5 avaient deja cherche une alternative avant notre interview" (fait)

---

## Framework d'analyse post-interview

### Pour chaque retour, se demander :
1. **C'est un fait ou une opinion ?**
   - Fait = comportement passe observe
   - Opinion = prediction future, jugement de valeur
2. **C'est specifique ou generique ?**
   - Specifique = "jeudi dernier j'ai passe 2h a chercher comment exporter mes donnees"
   - Generique = "des fois c'est un peu lent"
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

### Hypothese : "Les utilisateurs veulent une fonctionnalite de collaboration"

- "Tu utiliserais une fonctionnalite de partage en temps reel ?"
  → Tout le monde dit oui. Ca ne vaut rien.

- "La derniere fois que t'as travaille a plusieurs sur un doc, ca s'est passe comment ?"
  → Comportement reel. La friction existe-t-elle vraiment ?

- "T'as deja perdu du travail parce que quelqu'un a ecrase tes modifs ?"
  → Anecdote concrete. Douleur mesurable.

### Hypothese : "Les managers enverraient l'outil a leur equipe"

- "Vous recommanderiez notre outil a votre equipe ?"
  → Bien sur qu'ils disent oui. Ca ne vaut rien.

- "Qu'est-ce que vous envoyez a votre equipe pour se coordonner ? Comment ca se passe ?"
  → Workflow reel. Friction reelle ou non.

- "Votre equipe utilise quoi aujourd'hui ? Pourquoi pas autre chose ?"
  → Fait observe. Le probleme existe-t-il vraiment ?
