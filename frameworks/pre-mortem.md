# Pre-Mortem

## Quand l'utiliser

- Avant tout lancement/décision engageante (produit, investissement, hire, partenariat)
- Avant de signer un contrat majeur
- Quand l'équipe est unanimement enthousiaste (signal d'alerte)
- L'utilisateur dit "je vais lancer X", "je m'engage sur Y"

## Procédure

1. **Se téléporter** 12 mois dans le futur, à un moment où le projet **a échoué**.
2. **Écrire un faire-part d'obsèques** du projet : "Le projet X est mort le [date]. Il a échoué à cause de Y."
3. **Lister toutes les causes plausibles** de cette mort (même peu probables) : 8-12 causes.
4. **Pour chaque cause, évaluer** : probabilité (faible/moyenne/forte) × impact (réversible/irréversible).
5. **Les causes à forte probabilité OU impact irréversible** deviennent des **garde-fous** à mettre en place AVANT le lancement.
6. **Rédiger un plan d'atténuation** concret pour chaque garde-fou.

## Format synthèse

```
🧠 Framework : Pre-Mortem
📌 Pourquoi ce cadre : tu vas lancer, faut voir la mort avant

12 mois plus tard, le projet a échoué parce que :

1. <cause> — proba <F/M/F> × impact <R/IR>
2. <cause> — proba <F/M/F> × impact <R/IR>
3. <cause> — proba <F/M/F> × impact <R/IR>

Garde-fous prioritaires (forte proba OU irréversible) :
- <garde-fou 1>
- <garde-fou 2>

✅ Action : mettre en place <garde-fou #1> avant le lancement
⚠️ Angle mort : la cause "silencieuse" qu'on ne veut pas voir (regarde dans les causes "faible proba", il y en a souvent une)
```

## Format deep-dive

1. **Description du projet/décision** et de son succès attendu
2. **Téléportation** : date précise future + phrase d'obsèques
3. **Autopsie** : 10-15 causes d'échec (brainstorm sans filtre)
4. **Matrice proba × impact** sous forme de tableau 2x2 (ou 3x3)
5. **Causes critiques** (forte proba + fort impact) : analyse approfondie
6. **Plan d'atténuation** : pour chaque cause critique, une action préventive
7. **Seuils d'alerte** : quels signaux indiqueront qu'une cause se matérialise ?
8. **Décision finale** : GO / NO GO / GO sous conditions, avec conditions explicites

## Exemple bref

**Projet** : *"Je lance une formation en ligne à 997€ dans 2 mois, j'espère 200 ventes"*

12 mois plus tard, ça a raté parce que :
1. Audience pas assez chaude à l'achat — forte proba × impact moyen
2. Contenu trop long à produire, je décide de reporter — forte proba × impact fort
3. Plateforme technique bug le jour J — moyenne × fort (réversible mais coûteux)
4. Je perds la motivation après le lancement si les ventes sont tièdes — forte × fort
5. Un concurrent sort la même chose en gratuit — faible × irréversible
6. Positionnement unclear, les gens ne comprennent pas l'offre — moyenne × fort

Garde-fous prioritaires :
- Pré-vendre 20 places AVANT de finir le contenu (attaque #1 et #2)
- Définir un MVP de contenu (5 modules, pas 15)
- Avoir un plan de nurture pour les non-acheteurs (attaque #4)

✅ Action : cette semaine, lancer un appel à candidats "early access" à 497€ pour valider #1.
⚠️ Angle mort : cause #5 (concurrent gratuit) — surveiller ManyChat/Circle/Kajabi launch calendar.

## Pièges à éviter

- Ne pas faire un pre-mortem "pour se rassurer". Le but est de tuer le projet maintenant si c'est mort-né.
- Ne pas bloquer sur des causes faible proba + faible impact. Filtrer.
- Si l'équipe rejette le pre-mortem ("on est négatifs, ça démoralise") → c'est exactement pour ça qu'il faut le faire.
- Le pre-mortem n'est pas un "risques identifiés" de document corporate. C'est un exercice de simulation cruelle.
