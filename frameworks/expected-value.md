# Expected Value

## Quand l'utiliser

- Choix entre options avec **incertitude** sur les résultats
- Tu as une intuition sur les probabilités mais besoin de structurer
- L'utilisateur parle de "chance", "risque", "si ça marche / si ça marche pas"
- Décision d'investissement ou d'engagement de ressources

## Procédure

1. **Lister les options** (au moins 2, y compris "ne rien faire").
2. **Pour chaque option, identifier les scénarios** : succès / échec / intermédiaires.
3. **Estimer une probabilité** pour chaque scénario (en %). Note : être honnête sur l'incertitude — un 50/50 est acceptable s'il est vrai.
4. **Chiffrer le résultat** de chaque scénario (€, temps, impact — une unité cohérente).
5. **Calculer l'EV** = Σ (probabilité × résultat) pour chaque option.
6. **Comparer** les EV et la dispersion (écart-type mental : option A à EV=100 avec scénarios [80, 120] est plus sûre que option B à EV=100 avec scénarios [-500, 700]).
7. **Décider** selon EV mais AUSSI selon ton appétit au risque et la capacité à absorber le pire scénario.

## Format synthèse

```
🧠 Framework : Expected Value
📌 Pourquoi ce cadre : faut sortir de l'intuition binaire "ça marchera/pas"

Option A : <nom>
  - Succès (<p>%) : <gain>
  - Échec (<p>%) : <perte>
  - EV : <calcul>

Option B : <nom>
  - Succès (<p>%) : <gain>
  - Échec (<p>%) : <perte>
  - EV : <calcul>

Option C (baseline, ne rien faire) : EV = 0

EV le plus haut : <option>
Dispersion la plus faible : <option>

✅ Action : <option retenue>, parce que <EV + tolérance au risque>
⚠️ Angle mort : tes probabilités sont des estimations — si un scénario change de 10%, est-ce que la décision change ?
```

## Format deep-dive

1. **Cadre de décision** : horizon temporel, ressource engagée, ressource maximum perdable
2. **Options** (3-5) avec description courte chacune
3. **Arbre des scénarios** par option : tous les outcomes plausibles, pas juste binaire
4. **Probabilités** : source de l'estimation (data historique, base rate, jugement expert, pur guess) — être explicite
5. **Chiffrage** en unité cohérente (€, années de vie, impact)
6. **Table de calcul EV** pour chaque option
7. **Analyse de sensibilité** : à partir de quelle variation de probabilité la hiérarchie des options change ?
8. **Ruin check** : quelle option peut te faire perdre de manière irréversible ? (EV ne couvre pas la ruine)
9. **Décision finale** avec justification

## Exemple bref

**Question** : *"Je mets 50k€ dans ma startup OU je les garde en livret pour sécuriser 1 an de runway perso ?"*

Option A : tout dans la startup
- Startup décolle (30%) : +500k€ valeur equity dans 3 ans
- Startup stagne (50%) : capital rendu à 20k€
- Startup échoue (20%) : 0€
- EV = 0.3×500k + 0.5×20k + 0.2×0 = **160k€** à 3 ans

Option B : livret + rester salarié côté
- Sécurité garantie : 50k€ + intérêts (~52k€ dans 3 ans)
- EV = **52k€**

Option C : split 25k/25k
- EV ≈ 0.3×250k + 0.5×10k + 0.2×0 + 26k = **106k€**

EV le plus haut : Option A.
Mais **ruin check** : si option A échoue (20%), je n'ai plus de cash perso — je dois retourner salarié en urgence = coût caché.

✅ Action : Option C si ruin check me fait peur (ça fait 80% de chance de ne pas être ruiné et garde 60% de l'upside).
⚠️ Angle mort : la probabilité de succès de ta startup est quasi-certainement biaisée haut par ton optimisme. Fais tourner avec 15% au lieu de 30% et regarde.

## Pièges à éviter

- **Ne pas hallucinater des probabilités précises.** "70% de succès" sans justification est une invention. Préférer des fourchettes honnêtes.
- **EV ≠ décision finale.** Une option EV-positive peut être refusée si le pire scénario est la ruine.
- **Attention aux queues épaisses.** Si une option a un scénario à très faible proba mais à impact catastrophique (fraude, perte totale), l'EV moyen masque le vrai risque.
- **Ne pas oublier l'option "ne rien faire".** Elle a souvent une EV > 0.
- Ce framework ne marche **pas** pour les décisions de valeurs personnelles ou existentielles (carrière, relations). Utiliser `circle-of-competence` ou `10-10-10` à la place.
