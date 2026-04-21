# Cas de test — thinking-os

Ces 10 prompts couvrent les principaux chemins de la skill. Pour chacun, on vérifie :
- Le **routage** : la skill a-t-elle choisi le bon framework ?
- L'**application** : la réponse applique-t-elle vraiment le framework à la situation (vs générique) ?
- Le **format** : synthèse par défaut + possibilité de deep-dive
- Les **règles** : pas de name-dropping, pas d'empilement de frameworks, action actionnable

## Comment tester

Pour chaque cas, pose le prompt à Claude avec la skill chargée. Vérifie ensuite :
1. Le framework annoncé correspond-il au framework attendu ?
2. Le contenu applique-t-il le framework au cas spécifique (pas de blabla générique) ?
3. Y a-t-il une action claire et un angle mort identifié ?
4. Si tu demandes "détaille", la skill produit-elle bien un deep-dive structuré différent de la synthèse ?

---

## Cas 1 — Décomposition d'un présupposé

**Prompt** : *"On m'a toujours dit qu'il faut avoir un cofondateur pour réussir une startup. C'est vrai ?"*

**Framework attendu** : `first-principles`
**Pourquoi** : l'utilisateur remet en cause une convention répétée, signal classique de first-principles.

**Red flags** (à éviter) :
- La skill utilise `expected-value` (il n'y a pas de choix à faire ici)
- La skill sort une liste générique "avantages/inconvénients du cofondateur" sans démonter les hypothèses

---

## Cas 2 — Décision en cascade

**Prompt** : *"Je pense baisser les prix de mon SaaS de 30% pour gagner des parts de marché. Ça tient ?"*

**Framework attendu** : `second-order`
**Pourquoi** : décision avec effets en cascade (clients existants, concurrents, positionnement).

**Red flags** :
- La skill ne regarde que l'ordre 1 (plus de ventes)
- La skill propose un calcul EV sans voir les dynamiques relationnelles

---

## Cas 3 — Éviter l'échec

**Prompt** : *"Je veux que ma formation en ligne cartonne. Comment m'assurer de ne pas me planter ?"*

**Framework attendu** : `inversion`
**Pourquoi** : l'utilisateur demande explicitement "comment ne pas me planter" → signal direct d'inversion.

**Red flags** :
- La skill sort un plan de lancement classique au lieu de lister les modes d'échec

---

## Cas 4 — Situation compétitive rapide

**Prompt** : *"Mon concurrent direct vient d'annoncer une feature qu'on avait prévu de lancer dans 2 semaines. Qu'est-ce que je fais ?"*

**Framework attendu** : `ooda-loop`
**Pourquoi** : contexte compétitif + contrainte de temps + besoin de décider vite.

**Red flags** :
- La skill prend le temps d'une analyse `second-order` approfondie (trop lent pour la situation)
- La skill sort un `pre-mortem` (c'est post-lancement, pas pré)

---

## Cas 5 — Avant un engagement

**Prompt** : *"Je vais signer un partnership stratégique avec une grosse boîte dans 3 semaines. Je veux être sûr de pas me faire avoir."*

**Framework attendu** : `pre-mortem`
**Pourquoi** : avant engagement irréversible + "pas me faire avoir" = chercher modes d'échec futurs.

**Red flags** :
- La skill fait un `5-whys` sur un problème qui n'existe pas encore
- La skill sort une liste de clauses contractuelles (c'est du conseil juridique, hors scope)

---

## Cas 6 — Diagnostic problème récurrent

**Prompt** : *"Mes users se désinscrivent en masse au bout de 2 semaines. J'ai amélioré l'onboarding 3 fois, rien n'y fait."*

**Framework attendu** : `5-whys`
**Pourquoi** : problème récurrent + interventions déjà tentées sur les symptômes.

**Red flags** :
- La skill fait une liste de "conseils rétention"
- La skill applique `first-principles` (pas faux, mais `5-whys` est plus direct ici)

---

## Cas 7 — Arbitrage avec incertitude

**Prompt** : *"J'ai 20k€. Soit je les mets en ads pour accélérer la croissance, soit je hire un freelance pour refondre le produit. Honnêtement je sais pas."*

**Framework attendu** : `expected-value` (préféré) ou `opportunity-cost` (acceptable)
**Pourquoi** : arbitrage de ressource rare avec scénarios incertains.

**Red flags** :
- La skill applique les deux en même temps
- La skill donne juste un avis ("je pense que X est mieux") sans structurer

---

## Cas 8 — Hors cercle de compétence

**Prompt** : *"Un ami me propose d'investir dans une opération crypto yield farming, 8% par mois garantis. Il est sérieux, je le connais depuis 15 ans."*

**Framework attendu** : `circle-of-competence`
**Pourquoi** : domaine techniquement complexe + décision basée sur la relation, pas la compréhension + "8% par mois garantis" est un red flag (pas au framework de le dire explicitement, mais le cadre aide à voir qu'on est HORS cercle).

**Red flags** :
- La skill valide le deal sur la base de la confiance
- La skill fait un calcul EV avec les 8% comme acquis

---

## Cas 9 — Surcharge et priorisation

**Prompt** : *"J'ai 40 trucs à faire, tout semble urgent, je sais plus par où commencer."*

**Framework attendu** : `eisenhower`
**Pourquoi** : "tout semble urgent" + "par où commencer" = signature exacte.

**Red flags** :
- La skill produit un plan structuré de type roadmap sans classifier urgent/important
- La skill fait un `first-principles` sur pourquoi tu as autant de tâches (hors scope, trop méta)

---

## Cas 10 — Décision émotionnelle

**Prompt** : *"Ma co-founder m'a menti sur un deal important. Je veux racheter ses parts cette semaine et partir sur ma voie. J'en ai marre."*

**Framework attendu** : `10-10-10`
**Pourquoi** : signature émotionnelle forte ("j'en ai marre", "cette semaine") + décision irréversible (rachat + split). Priorité émotion selon règle "signature émotionnelle > autres".

**Red flags** :
- La skill applique `expected-value` sur les parts comme si c'était un calcul rationnel
- La skill donne un conseil juridique sur le rachat
- La skill minimise l'émotion ("tu devrais juste respirer")

---

## Cas bonus — Déclenchement explicite

**Prompt** : *"Applique un pre-mortem sur mon projet de lancer une newsletter payante le 15 juin."*

**Framework attendu** : `pre-mortem` (mode explicite)
**Pourquoi** : déclenchement direct par nom → skip routing, load directement `frameworks/pre-mortem.md`.

**Red flags** :
- La skill fait autre chose que `pre-mortem`
- La skill pose des questions de clarification inutiles avant d'appliquer

---

## Critères de validation globaux

Après les 11 cas, la skill est validée si :

- ✅ Au moins **9/11** cas ont le bon framework déclenché
- ✅ **100%** des réponses sont appliquées au contexte (aucune réponse générique)
- ✅ **100%** des réponses incluent une action claire + un angle mort
- ✅ Le mode deep-dive produit un contenu réellement plus structuré (pas juste plus long)
- ✅ Aucune réponse n'empile plusieurs frameworks sans demande explicite
- ✅ Aucune réponse ne cite de gourou/investisseur en mode "comme disait..."

Si un ou plusieurs critères échouent, itérer sur :
- La section "routeur" du `SKILL.md` (si mauvais framework choisi)
- La section "Format synthèse" du framework défaillant (si contenu générique)
- La règle "Ne pas empiler les frameworks" (si empilement détecté)
