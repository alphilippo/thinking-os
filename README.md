# thinking-os

> Un routeur cognitif pour Claude : détecte le type de problème posé et applique le bon framework de pensée au lieu de balancer des généralités.

## Ce que ça fait

La plupart des gens collectionnent des mental models comme des timbres puis n'en appliquent aucun correctement. `thinking-os` fait l'inverse :

1. **Diagnostique** automatiquement le type de problème (décision, arbitrage, diagnostic, compréhension, priorisation, décision émotionnelle)
2. **Sélectionne** le framework le plus adapté parmi 12
3. **Applique** rigoureusement ce framework au cas spécifique
4. **Produit** une synthèse courte avec action claire + angle mort, avec deep-dive disponible sur demande

## Les 12 frameworks

| Framework | Quand l'appliquer |
|---|---|
| **First Principles** | Remise à plat d'un sujet encombré de conventions |
| **Second-Order Thinking** | Décisions avec conséquences en cascade |
| **Inversion** | "Comment éviter l'échec" plutôt que "comment réussir" |
| **OODA Loop** | Situations compétitives rapides |
| **Pre-Mortem** | Avant un lancement/engagement irréversible |
| **5 Whys** | Diagnostic de cause racine |
| **Expected Value** | Arbitrage avec incertitude |
| **Opportunity Cost** | Arbitrage entre options connues |
| **Bayesian Update** | Intégrer une info nouvelle |
| **Circle of Competence** | "Suis-je qualifié pour décider ?" |
| **Eisenhower Matrix** | Priorisation urgent vs important |
| **10-10-10 Rule** | Décisions émotionnelles |

## Modes de déclenchement

**Mode auto (par défaut)** — Claude détecte via des signatures linguistiques :
- *"J'hésite entre X et Y"* → arbitrage
- *"Pourquoi ça marche pas"* → diagnostic
- *"Je vais lancer X"* → pre-mortem
- *"J'en ai marre"* → décision émotionnelle
- etc.

**Mode explicite** — Tu nommes le framework :
- *"Applique first principles sur X"*
- *"Fais-moi un pre-mortem de Y"*
- *"Utilise 10-10-10 sur cette décision"*

## Installation

### Pour Claude.ai (skills user)

1. Télécharge/clone ce dossier.
2. Place-le dans `/mnt/skills/user/thinking-os/` (ou ton équivalent selon ta config Claude.ai).
3. La skill se déclenche automatiquement sur les prompts qui matchent.

### Pour Claude Code

```bash
cp -r thinking-os ~/.claude/skills/
```

Puis vérifie avec `/plugin` que la skill apparaît dans tes skills disponibles.

### Pour l'API Claude

Packager le dossier en `.skill` et uploader via l'endpoint `/skills`. Voir la [doc officielle](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview).

## Exemples d'usage

### Décision d'investissement
> *"J'ai 50k€. Je les mets dans ma startup ou je les garde en sécurité ?"*

→ La skill détecte `expected-value`, chiffre les scénarios, sort une recommandation avec ruin check.

### Diagnostic produit
> *"Mes users se désinscrivent en masse. J'ai déjà refait l'onboarding 3 fois."*

→ La skill applique `5-whys`, remonte à la cause racine.

### Situation compétitive
> *"Le concurrent vient d'annoncer ma feature 2 semaines avant mon lancement."*

→ La skill applique `ooda-loop`, produit une action dans les 48h.

### Décision émotionnelle
> *"J'en ai marre, je veux démissionner demain."*

→ La skill applique `10-10-10`, protège l'utilisateur contre la décision réflexe.

## Structure

```
thinking-os/
├── SKILL.md                    # Métadonnées + routeur cognitif
├── README.md                   # Ce fichier
├── frameworks/                 # Un fichier par framework (chargement à la demande)
│   ├── first-principles.md
│   ├── second-order.md
│   ├── inversion.md
│   ├── ooda-loop.md
│   ├── pre-mortem.md
│   ├── 5-whys.md
│   ├── expected-value.md
│   ├── opportunity-cost.md
│   ├── bayesian.md
│   ├── circle-of-competence.md
│   ├── eisenhower.md
│   └── 10-10-10.md
├── examples/                   # Exemples bout-en-bout
│   ├── decision-example.md
│   ├── problem-example.md
│   └── emotional-example.md
└── tests/
    └── test-cases.md           # 11 prompts de validation
```

## Philosophie de design

- **Progressive disclosure** : le `SKILL.md` ne contient que le routeur. Les frameworks sont chargés à la demande pour ne pas noyer le contexte.
- **Un cadre à la fois** : la skill refuse d'empiler plusieurs frameworks sans demande explicite — sinon ça devient un séminaire Charlie Munger inutile.
- **Pas de name-dropping** : aucun "comme disait Buffett" sauf si c'est vraiment éclairant.
- **Priorité à l'émotion** : si la question contient des marqueurs émotionnels forts, `10-10-10` ou `circle-of-competence` passent devant les frameworks analytiques.
- **Format action-ready** : chaque sortie contient une action concrète + un angle mort. Pas de blabla.

## Limites

- Ne remplace pas un conseil financier, juridique ou médical professionnel.
- Les frameworks d'arbitrage reposent sur les probabilités estimées par l'utilisateur — ils n'en créent pas.
- Ne marche pas bien sur les questions d'info pure (*"c'est quoi la capitale du Chili ?"*) — la skill ne se déclenche pas, c'est voulu.

## Roadmap

- **v1.0** (actuel) : 12 frameworks + routeur auto + mode explicite
- **v1.1** : ajout de la Feynman Technique (apprentissage), Minto Pyramid (communication), Systems Thinking
- **v1.2** : mémoire des frameworks récemment utilisés pour éviter la répétition
- **v2.0** : combinaison explicite de frameworks (ex: `first-principles` + `inversion` pour démontage stratégique)

## Skill complémentaire

[**execution-os**](https://github.com/alphilippo/execution-os) — système d'exécution qui se compose avec thinking-os :
- `thinking-os` répond à **QUOI** faire (décisions, arbitrages, diagnostics)
- `execution-os` répond à **COMMENT** le faire réellement (sprint, deep work, rétro, accountability)

Utilisez-les ensemble pour passer de l'intention à l'exécution.

## Licence

Apache 2.0 — tu peux forker, adapter, republier. Si tu fais une fork utile, merci de partager le lien.

## Crédits

Conçu avec Claude comme Skill Architect. Inspiré par les travaux de Charlie Munger (mental models), Ray Dalio (principles), Shane Parrish (Farnam Street), et la tradition OODA de John Boyd.
