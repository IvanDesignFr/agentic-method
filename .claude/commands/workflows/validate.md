---
description: Checklist post-implementation. Verifie tokens, code quality, responsive, accessibilite. Usage: /validate [fichier-ou-scope]
---

# Validate

**Session ID:** ${CLAUDE_SESSION_ID}

## Scope

Identifier les fichiers modifies depuis le dernier commit :
```bash
git diff --name-only HEAD
git diff --cached --name-only
```

Si `$ARGUMENTS` est fourni, limiter la validation a ce scope.

---

## 5 passes de validation

Executer chaque passe sequentiellement. Reporter les resultats dans le tableau final.

### Pass 1 — Design System Tokens

Verifier dans les fichiers CSS/JS modifies :
- Pas de couleurs hex hardcodees (sauf dans `variables.css` ou `tokens.json`)
- Pas de `px` hardcodes pour spacing/radius/font-size (sauf `1px` pour borders et `0`)
- Pas de `box-shadow` hardcodees
- Pas de `z-index` hardcodes
- Pas de `font-family` hardcodees
- Toutes les valeurs passent par `var(--...)`

**Methode :** Grep dans les fichiers CSS modifies pour detecter les patterns hardcodes.

### Pass 2 — Code Quality

Verifier :
- Pas de `console.log` / `console.warn` / `console.error` oublies (sauf dans des error handlers)
- Pas de `TODO` / `FIXME` / `HACK` ajoutes
- Pas de code commente laisse
- Pas de `debugger`
- Pas de style inline (`style="..."`) dans le HTML/JS

**Methode :** Grep dans tous les fichiers modifies.

### Pass 3 — Responsive

Verifier pour chaque composant UI modifie :
- [ ] **Desktop** (>968px) : layout correct
- [ ] **Tablette** (<=968px) : layout horizontal -> vertical, panels 100% width
- [ ] **Mobile** (<=600px) : spacing compresse, titres reduits
- [ ] **Petit mobile** (<=400px) : headlines reduits

**Methode :** Lire le CSS du composant et verifier la presence des media queries pertinentes. Si le composant a un layout (flex/grid), les 3 breakpoints doivent etre geres.

### Pass 4 — Accessibilite

Verifier :
- `prefers-reduced-motion: reduce` si des animations sont ajoutees
- Focus states presents (`:focus-visible`) si des elements interactifs sont ajoutes
- Contrastes respectes via tokens (`accent-text` et non `accent-blue` pour texte)
- `aria-label` ou texte accessible pour les boutons/icons sans texte
- Pas de `outline: none` sans remplacement

**Methode :** Grep + lecture ciblee du CSS/HTML modifie.

### Pass 5 — Coherence Design System

Verifier les patterns d'usage :
- CTA primaires = gradient (pas aplat)
- CTA secondaires = ghost (transparent + bordure)
- Cards = `bg-card` + `border-thin` + `radius-2xl`
- Hover cards = `translateY(-4px)` + `border-accent`
- Hover boutons = `translateY(-2px)` + `shadow-md`
- Transitions = `transition-fast` pour hover

**Methode :** Lecture ciblee des composants modifies.

---

## Output

```markdown
## Validation: [scope ou fichiers]

| Pass | Statut | Details |
|------|--------|---------|
| 1. Tokens | OK/WARN/FAIL | [details si probleme] |
| 2. Code Quality | OK/WARN/FAIL | [details si probleme] |
| 3. Responsive | OK/WARN/SKIP | [details ou "pas de composant UI modifie"] |
| 4. Accessibilite | OK/WARN/SKIP | [details ou "pas d'element interactif ajoute"] |
| 5. Coherence DS | OK/WARN/FAIL | [details si probleme] |

### Problemes trouves
- [ ] [Description du probleme 1 + fichier:ligne]
- [ ] [Description du probleme 2 + fichier:ligne]

### Verdict: PASS / PASS avec warnings / FAIL
```

**Regles :**
- SKIP est autorise si la passe n'est pas pertinente (ex: pas d'UI modifiee -> skip responsive)
- WARN = non bloquant mais a corriger idealement
- FAIL = bloquant, corriger avant commit
- Proposer les corrections pour chaque FAIL trouve

---

## Demarrage

**Scope :** $ARGUMENTS

Je lance la validation sur les fichiers modifies...
