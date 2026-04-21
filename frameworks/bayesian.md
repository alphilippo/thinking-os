# Bayesian Update

## Quand l'utiliser

- Une nouvelle info arrive qui pourrait changer ta conviction
- Tu veux savoir **combien** cette info doit faire bouger ton opinion
- Tu sens que tu sur-réagis ou sous-réagis à une data nouvelle
- L'utilisateur dit "je viens d'apprendre que...", "nouvelle data", "ça change quoi ?"

## Procédure

1. **Formuler la croyance actuelle** (hypothèse H) : "Je pense que X est vrai."
2. **Estimer la probabilité initiale** P(H) — ta conviction avant la nouvelle info, en %.
3. **Identifier la nouvelle info** (évidence E).
4. **Se demander** : "Si H est vrai, quelle probabilité qu'on observe E ?" → P(E|H)
5. **Se demander** : "Si H est faux, quelle probabilité qu'on observe E quand même ?" → P(E|¬H)
6. **Appliquer Bayes** en version intuitive :
   - Si P(E|H) **>>** P(E|¬H) → l'info pousse fortement vers H. Augmenter conviction.
   - Si P(E|H) ≈ P(E|¬H) → l'info est neutre, ne rien changer.
   - Si P(E|H) **<<** P(E|¬H) → l'info pousse contre H. Diminuer conviction.
7. **Estimer la nouvelle probabilité** P(H|E) — ta conviction révisée, en %.

## Format synthèse

```
🧠 Framework : Bayesian Update
📌 Pourquoi ce cadre : nouvelle info → quelle révision de conviction ?

Croyance initiale : <H>
P(H) avant : <X>%

Évidence nouvelle : <E>
Si H vrai, proba d'observer E : <haute / moyenne / faible>
Si H faux, proba d'observer E : <haute / moyenne / faible>

Direction du shift : <pro-H / anti-H / neutre>
Magnitude du shift : <fort / modéré / faible>

P(H) après : <Y>% (ancienne <X>% → nouvelle <Y>%)

✅ Action : <comment cette révision change ton comportement>
⚠️ Angle mort : cette évidence seule ne devrait pas faire basculer si ta conviction initiale était forte et basée sur beaucoup d'autres évidences
```

## Format deep-dive

1. **Hypothèse H** précisément formulée
2. **Base rate** : quelle proportion de cas similaires ont effectivement H vrai ? (si data dispo)
3. **P(H) prior** : ta conviction avant, justifiée par tes évidences déjà en main
4. **Évidence E** : description précise, source, fiabilité
5. **Likelihood ratio** : P(E|H) / P(E|¬H), estimé qualitativement
6. **Force de l'évidence** : forte si ratio >10 ou <0.1 ; faible si ratio proche de 1
7. **P(H|E) posterior** : conviction révisée
8. **Scénarios contrefactuels** : quelle autre évidence aurait pu produire un shift inverse ?
9. **Action révisée** avec seuil : à quel posterior je change de comportement ?

## Exemple bref

**H** : *"Ma feature X va être adoptée par au moins 20% des users au bout d'un mois."*
P(H) avant : 60% (basé sur intuition + feedback initial).

**E** : *"En beta fermée (50 users), seulement 3 utilisent X activement au bout de 2 semaines."*

P(E|H) : si la feature va vraiment réussir, la probabilité d'observer seulement 6% d'adoption en beta à S2 est **faible** (~15%). Normalement en beta, les enthousiastes adoptent vite.

P(E|¬H) : si la feature va échouer, la probabilité d'observer 6% en beta est **élevée** (~60%). C'est exactement ce pattern-là qu'on voit.

Ratio P(E|H) / P(E|¬H) = 0.15 / 0.60 = 0.25 → **shift fort contre H**.

P(H) après : 60% × 0.25 = ~20% (très approximatif mais la direction est claire : ta conviction devrait descendre fort).

✅ Action : avant de lancer en prod, faire un cycle d'user research pour comprendre les 47 users non-adopteurs. Ne pas lancer si on n'a pas de pivot.
⚠️ Angle mort : 50 users c'est petit. Si la beta est biaisée (early adopters non représentatifs du marché réel), P(E|H) et P(E|¬H) changent.

## Pièges à éviter

- **Ne pas fabriquer des probabilités précises.** Bayes marche avec des estimations grossières ; ce qui compte c'est la direction et la magnitude.
- **Piège du base rate.** Si H est une hypothèse rare (ex: "ma startup sera une licorne"), même une évidence forte ne suffit pas à la rendre probable — c'est le problème classique de sur-réagir aux bonnes nouvelles.
- **Ne pas over-update sur une seule évidence.** Ta conviction antérieure compte ; 10 évidences pour H et 1 contre ne doivent pas renverser.
- **Attention aux évidences corrélées.** 3 personnes du même groupe qui disent la même chose = 1 évidence, pas 3.
- Ce framework est un outil de calibration, pas un oracle. Si le résultat te surprend, questionne tes probabilités d'entrée avant de questionner Bayes.
