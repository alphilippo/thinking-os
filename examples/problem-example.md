# Exemple 2 — Diagnostic de problème récurrent

**Prompt utilisateur** :
> *"Mon équipe livre toujours en retard. On a changé d'outil, on a fait des rétros, ça change rien. J'arrive pas à comprendre pourquoi."*

---

## Ce que la skill fait (mode auto)

**Détection** : signature "toujours en retard" + "j'arrive pas à comprendre pourquoi" + "on a essayé X et Y, ça change rien" → classique 5-Whys.

**Framework sélectionné** : `5-whys`.

---

## Sortie (mode synthèse, par défaut)

🧠 **Framework : 5 Whys**
📌 **Pourquoi ce cadre** : tu traites les symptômes (outils, rétros), faut la cause racine

**Problème** : l'équipe livre en retard de façon systématique.

Pourquoi ? → Les estimations ne sont jamais tenues.
Pourquoi ? → Les tâches explosent en cours de route à cause de spécifications incomplètes.
Pourquoi ? → Les specs sont rédigées par une seule personne (PM) sans input technique en amont.
Pourquoi ? → Le PM veut "protéger" les devs de la discovery et les laisser coder.
Pourquoi ? → C'est une culture importée d'une ancienne boîte où les devs étaient juniors — mais tes devs sont seniors et veulent du contexte.

**Cause racine** : asymétrie d'info entre PM et devs, héritée d'une culture qui ne correspond plus à la séniorité de l'équipe.

✅ **Action** : introduire un "3 amigos" (PM + lead dev + QA) en amont de chaque spec critique. Démarrer sur le prochain sprint, mesurer le taux de tenue d'estimation à 4 semaines.

⚠️ **Angle mort** : la cause racine a elle-même une cause ("le PM ne sait pas faire autrement"), mais c'est un sujet de coaching/embauche, pas de process. Pour l'instant tu agis sur le process.

---

## Si l'utilisateur dit "deep-dive" ensuite

La skill charge la section "Format deep-dive" de `frameworks/5-whys.md` et produit :

1. Énoncé factuel avec data (nombre de sprints ratés, % de délai, impact business)
2. Chaîne de "pourquoi" en détail, chaque lien logique justifié
3. Vérification : à chaque niveau, existait-il une autre réponse plausible ? Pourquoi celle-là et pas une autre ?
4. Cause racine confirmée par un test mental (si on la corrige, les symptômes disparaissent-ils ?)
5. Plan d'action séquencé (semaines 1-2-4-8)
6. Indicateurs de suivi : taux de tenue d'estimation, temps de découverte par ticket, satisfaction devs
7. Scénario de repli si après 4 semaines rien n'a bougé — signal qu'une autre cause racine existe
