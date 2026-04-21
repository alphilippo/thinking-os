# Instructions push GitHub — thinking-os

## Étape 1 — Créer le repo sur GitHub

1. Va sur https://github.com/new
2. Repository name : `thinking-os`
3. Description : `A cognitive router skill for Claude — applies the right thinking framework to the right problem`
4. Public ✅
5. **Ne coche PAS** "Add a README", "Add .gitignore", "Choose a license" (on les a déjà)
6. Clique "Create repository"

## Étape 2 — Push depuis ta machine

Dézippe le fichier `thinking-os-github.zip` que je t'ai fourni, puis dans ton terminal :

```bash
cd thinking-os-github
git init
git add .
git commit -m "Initial release: thinking-os v1.0 with 12 frameworks"
git branch -M main
git remote add origin https://github.com/<TON-USERNAME>/thinking-os.git
git push -u origin main
```

Remplace `<TON-USERNAME>` par ton vrai username GitHub.

## Étape 3 — Configurer le repo (5 min)

Sur la page du repo GitHub :

1. **About** (côté droit) → clique l'engrenage :
   - Description : `Cognitive router skill for Claude — detects problem type and applies the right thinking framework`
   - Website : laisse vide pour l'instant
   - Topics : `claude`, `claude-skill`, `mental-models`, `decision-making`, `thinking-frameworks`, `ai-agent`
2. **Settings** → **General** → **Features** : désactive `Wiki` (inutile pour une skill), laisse `Issues` actif
3. **Settings** → **Pages** : pas nécessaire pour l'instant

## Étape 4 — Amorcer la visibilité

### Immédiat (15 min)
- Post LinkedIn court : "Je viens de publier une skill Claude open-source qui applique le bon framework de pensée à chaque type de problème. 12 frameworks, routage automatique. Lien [URL]."
- Post Twitter/X : même chose en version courte avec le lien
- Si tu as un site/blog : ajoute une mention

### Cette semaine
- Soumettre à **skillsmp.com** (il aggrège les skills GitHub automatiquement, mais une soumission directe accélère)
- Soumettre à **claudemarketplaces.com**
- Partager dans 1-2 communautés Discord/Slack dédiées à Claude / AI / productivity

### Ce mois-ci
- Écrire un post Medium/Substack qui explique UN framework en détail (ex: "How I use Pre-Mortem to de-risk product launches") et référence ton repo
- Si possible, obtenir une mention dans la newsletter de Simon Willison, Latent Space, ou équivalent

## Étape 5 — Monitorer

Check une fois par semaine :
- Stars (un indicateur léger de traction)
- Issues ouvertes (feedback direct)
- Traffic → Insights → Traffic (sources de visites = tu sauras d'où viennent les gens)

## Ce qu'il faut PAS faire

- Pas spammer des groupes LinkedIn avec le lien
- Pas créer des comptes fake pour booster les stars
- Pas promettre des mises à jour que tu ne livreras pas
- Pas publier v1.1 avant d'avoir au moins 2 semaines d'usage réel sur v1.0
