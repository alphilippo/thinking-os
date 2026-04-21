# Contributing to thinking-os

Merci de vouloir contribuer. Ce projet est une skill Claude open-source — les contributions les plus utiles sont celles qui améliorent la **précision du routeur** ou qui ajoutent des **frameworks rigoureusement définis**.

## Les 3 types de contributions bienvenues

### 1. Nouveaux frameworks

Si tu veux proposer un nouveau framework de pensée, il doit respecter ces critères :

- **Unique** : il ne doit pas faire doublon avec un framework existant. Ex: "mental models" n'est pas un framework, c'est une catégorie.
- **Actionnable** : appliqué à un cas réel, il doit produire une action concrète, pas une réflexion flottante.
- **Enseignable en 1 page** : s'il faut un livre pour l'expliquer, il est trop complexe pour cette skill.
- **Universel** : ne doit pas dépendre d'un domaine spécifique (ex: "DCF valuation" est trop finance-specific).

Pour proposer un framework, ouvre une PR qui ajoute :
- `frameworks/<nom>.md` en suivant la structure des frameworks existants (quand l'utiliser, procédure, format synthèse, format deep-dive, exemple bref, pièges)
- Une mise à jour de `SKILL.md` dans la table du routeur
- Un nouveau cas dans `tests/test-cases.md`

### 2. Amélioration du routeur

Si tu observes que la skill se déclenche mal sur certains prompts, documente le cas dans une issue avec :
- Le prompt exact
- Le framework actuellement déclenché
- Le framework qui devrait être déclenché
- Ta proposition de signature linguistique à ajouter

### 3. Nouveaux exemples / cas de test

Plus on a de cas concrets variés, mieux la skill apprend à se déclencher correctement. PR bienvenues pour ajouter dans `examples/` ou `tests/test-cases.md`.

## Ce qu'on refuse

- Ajout de "mental models" génériques sans procédure actionnable (Occam's razor, Hanlon's razor, etc. — utiles mais pas adaptés au format "framework avec procédure")
- Frameworks qui se recouvrent à plus de 70% avec un existant
- Name-dropping gratuit ("comme disait Buffett...")
- Scripts complexes (on veut rester 100% markdown pour la portabilité)

## Style

- **Français ou anglais accepté**, mais chaque framework doit être dans une seule langue de bout en bout
- **Ton direct** : pas de sugar-coating, pas de "il semblerait que..."
- **Exemples concrets** : chaque framework a un exemple sur un cas réel (startup, relation, décision pro)

## Process

1. Fork le repo
2. Crée une branche `feat/<nom-du-framework>` ou `fix/<nom-du-bug>`
3. Commit avec un message clair : `feat: add <framework>` ou `fix: router triggers expected-value on emotional prompts`
4. Ouvre une PR avec :
   - Description du changement
   - Cas de test qui valident l'ajout
   - Screenshot ou exemple de sortie si applicable

## Code de conduite

Soyez rigoureux avec les idées, gentils avec les personnes. Les débats intellectuels sont bienvenus, les attaques personnelles non.

Merci pour ton aide à construire un meilleur outil de pensée pour tout le monde.
