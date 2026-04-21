# Opportunity Cost

## Quand l'utiliser

- Arbitrage entre options concrètes et connues (pas d'incertitude majeure)
- Tu hésites entre A et B avec des résultats assez visibles
- L'utilisateur dit "je ferais bien X mais aussi Y"
- Ressource limitée (temps, cash, attention) à allouer

## Procédure

1. **Reconnaître la ressource rare** : temps, cash, attention, capital humain. Une seule à la fois.
2. **Lister les options** en compétition pour cette ressource.
3. **Pour chaque option**, évaluer le **bénéfice attendu** (pas l'EV — juste ce qui est visiblement produit).
4. **Identifier l'option retenue** → c'est le "coût d'opportunité" des autres.
5. **Poser la question inverse** : si je choisis A, qu'est-ce que je **perds** en ne choisissant pas B ? Est-ce tolérable ?
6. **Vérifier** que l'option retenue est celle dont la non-réalisation serait la plus regrettable dans 1 an.

## Format synthèse

```
🧠 Framework : Opportunity Cost
📌 Pourquoi ce cadre : tu as une ressource rare, faut arbitrer

Ressource rare : <temps/cash/attention>, quantité : <X>

Option A : <description> — bénéfice : <B_A>
Option B : <description> — bénéfice : <B_B>
Option C : <description> — bénéfice : <B_C>

Choisir A = renoncer à B et C
Test du regret : dans 1 an, laquelle je regretterai le plus de ne pas avoir faite ?

✅ Action : <option qui passe le test du regret>
⚠️ Angle mort : l'option "ne rien faire" compte — elle a un coût aussi (status quo qui se dégrade)
```

## Format deep-dive

1. **Définition de la ressource rare** : quantité précise, période d'allocation
2. **Inventaire des options** (3-7) avec description, bénéfice, horizon de réalisation
3. **Complémentarités** : y a-t-il des options compatibles (A+C fractionné) ?
4. **Matrice** : options × bénéfices attendus par dimension (financier, apprentissage, impact, plaisir)
5. **Test du regret** projeté à 1, 3, 10 ans
6. **Test de réversibilité** : quelle option est la plus réversible ? (priorise le réversible quand l'incertitude est forte)
7. **Décision** avec clause d'ajustement (à quelle condition on rebascule sur une autre option)

## Exemple bref

**Question** : *"J'ai 20h/semaine de temps libre. Je lance un podcast, je fais du sport sérieusement, ou j'apprends le ML ?"*

Ressource rare : 20h/semaine, horizon : 6 mois.

Option A : Podcast — bénéfice : visibilité + réseau + skill storytelling
Option B : Sport sérieux — bénéfice : santé + énergie + discipline
Option C : ML — bénéfice : compétence technique + option de pivot

Test du regret à 1 an :
- Si je n'ai pas fait le podcast : "dommage, mais je peux démarrer à tout moment"
- Si je n'ai pas fait le sport : "je suis physiquement diminué, ça impacte tout le reste"
- Si je n'ai pas fait le ML : "le train passe, mais je peux rattraper"

Le regret maximum = sport non fait, parce qu'il est l'enabler des deux autres.

✅ Action : 8h/sem sport (base) + 12h/sem split podcast OU ML selon énergie résiduelle.
⚠️ Angle mort : "split" est souvent une illusion — en vrai tu feras 1 à 80% et l'autre à 20%. Choisis quelle option est la primaire.

## Pièges à éviter

- **Ne pas confondre coût d'opportunité et FOMO.** Le FOMO te fait voir toutes les options ; l'OC te fait en choisir une consciemment.
- **Le coût d'opportunité n'est pas toujours visible.** Choisir "garder mon job" a un coût d'opportunité qu'on n'évalue jamais (les business qu'on ne lance pas).
- **Options non-exclusives** : parfois A et B peuvent coexister à 50% chacun. Mais attention à la dispersion d'énergie.
- **Time-boxing** : un choix d'allocation n'est pas éternel. Set une date de review (ex: 3 mois) où tu peux re-arbitrer.
- Ce framework présuppose qu'on connaît assez bien les options. Si c'est flou, commencer par `first-principles`.
