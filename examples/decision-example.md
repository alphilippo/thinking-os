# Exemple 1 — Arbitrage d'investissement

**Prompt utilisateur** :
> *"J'ai 50k€ sur le côté. Je peux les mettre dans ma startup qui a besoin de cash pour tenir 6 mois, ou les garder en livret pour ma sécurité perso. J'hésite."*

---

## Ce que la skill fait (mode auto)

**Détection** : signature "j'hésite entre X et Y" + "j'ai [ressource] je peux la mettre dans X ou Y" → trigger clair pour `opportunity-cost`. Mais la présence d'incertitude forte ("startup qui a besoin de cash") fait basculer vers `expected-value`.

**Framework sélectionné** : `expected-value`.

---

## Sortie (mode synthèse, par défaut)

🧠 **Framework : Expected Value**
📌 **Pourquoi ce cadre** : tu arbitres entre deux options avec des résultats très différents selon les scénarios, faut sortir de l'intuition binaire

**Option A : 50k€ dans la startup**
- Startup atteint son prochain palier (35%) : tu débloques un tour plus gros, valeur equity future +400k€
- Startup survit mais stagne (40%) : tu récupères ~15k€ de valeur quand tu sors
- Startup échoue (25%) : 0€
- **EV ≈ 146k€ sur 3 ans**

**Option B : 50k€ en livret**
- Sécurité garantie : 50k + intérêts (~52k€ dans 3 ans)
- **EV ≈ 52k€**

**Option C : Split 25k/25k**
- EV ≈ 0.35×200k + 0.4×7.5k + 0.25×0 + 26k = **~99k€**

**EV le plus haut** : Option A.
**Dispersion la plus forte** : Option A aussi.
**Ruin check** : si Option A échoue (25%), tu n'as plus de coussin perso — tu dois retourner salarié en urgence.

✅ **Action** : Option C (split 25/25). Tu conserves 70% de l'upside tout en gardant 1 an de runway perso. Si la startup performe les 6 prochains mois, tu peux re-injecter les 25k€ restants avec meilleure info.

⚠️ **Angle mort** : tes 35% de succès sont probablement optimistes. Refais le calcul avec 20% de succès — si Option A reste gagnante, le choix est solide. Sinon c'est ton optimisme qui parle.

---

## Si l'utilisateur dit "deep-dive" ensuite

La skill charge la section "Format deep-dive" de `frameworks/expected-value.md` et produit :

1. Cadre de décision détaillé (horizon 3 ans, ressource max perdable = 50k€)
2. Options (3 versions chiffrées + variantes)
3. Arbre des scénarios par option avec sous-scénarios
4. Sources des probabilités (jugement perso, base rates startup, etc.)
5. Table de calcul détaillée
6. Analyse de sensibilité (qu'est-ce qui bascule la décision si probas bougent)
7. Ruin check approfondi
8. Décision finale avec clause de révision
