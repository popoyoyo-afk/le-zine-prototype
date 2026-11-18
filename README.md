# Le zine du quotidien — prototype

Prototype cliquable d'une app mobile d'alternatives écologiques (MVP), direction graphique « piste 2 — Fanzine ».

Le parcours : on scanne l'étiquette d'un vêtement, on voit d'où vient son impact (matière, lieu de fabrication, transport), puis on choisit une alternative du même rayon et au même budget. L'impact évité s'additionne dans l'onglet Impact.

## Contenu

| Fichier | Rôle |
| --- | --- |
| `index.html` | Le prototype complet : HTML, CSS et JavaScript, sans dépendance ni étape de build |
| `vercel.json` | Configuration du déploiement statique sur Vercel |
| `docs/plan-figma-mvp.md` | Plan de tâches, décisions de cadrage et état des écrans Figma |

## Lancer en local

Ouvrir `index.html` dans un navigateur. Il n'y a rien à installer. Les polices viennent de Google Fonts.

## Déployer sur Vercel

1. Sur [vercel.com/new](https://vercel.com/new), importer ce dépôt GitHub.
2. Laisser le preset sur **Other**, sans commande de build et avec le répertoire de sortie par défaut.
3. Cliquer sur **Deploy**. Chaque push sur `main` redéploie le site.

## À savoir

- Les chiffres d'impact sont fictifs mais cohérents entre les écrans. Ils sont à recaler sur Ecobalyse et la Base Empreinte® ADEME.
- Rien n'est enregistré ni envoyé : l'état de la démo repart de zéro à chaque rechargement.
