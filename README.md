# 🧮 Scientific Calculator — ALI NEON

Calculatrice scientifique au style néon, avec commande vocale (hors-ligne via Vosk, avec repli sur la reconnaissance vocale du navigateur) et synthèse vocale en français.

Application **100 % statique** : un seul fichier `index.html`, aucune étape de build, aucune dépendance à installer.

## Fonctionnalités

- Opérations scientifiques : `sin`, `cos`, `tan` (en degrés), `log`, `ln`, `√`, racine n-ième, puissances, `²`, `³`, `!`, `%`, `π`, `e`
- Reconnaissance vocale hors-ligne (Vosk, modèle français) avec repli en ligne
- Lecture vocale des résultats
- Installable (PWA) et interface adaptée au mobile

## Lancer en local

Ouvrez simplement `index.html` dans un navigateur, ou servez le dossier :

```bash
python3 -m http.server 8080
# puis http://localhost:8080
```

> Le micro et le service worker exigent `https://` ou `localhost`.

## Déploiement

Le projet est un site statique : la racine du dépôt est le dossier à publier.

| Plateforme | Configuration |
|---|---|
| **GitHub Pages** | Workflow inclus (`.github/workflows/pages.yml`). Dans *Settings → Pages → Source*, choisir **GitHub Actions**. |
| **Netlify** | Importer le dépôt — `netlify.toml` inclus (aucun build). |
| **Vercel** | Importer le dépôt — `vercel.json` inclus (aucun build). |
| **Cloudflare Pages** | Framework : *None*, build command : vide, output directory : `/`. |
| **Docker** | `docker build -t calculator . && docker run -p 8080:80 calculator` |
| **Tout hébergement** | Copier `index.html` sur n'importe quel serveur web. |

## Dépendances externes (chargées à l'exécution)

- [`vosk-browser@0.0.8`](https://www.npmjs.com/package/vosk-browser) via jsDelivr
- Modèle vocal `vosk-model-small-fr-0.22` depuis alphacephei.com (~50 Mo, téléchargé une fois)
- Police Orbitron via Google Fonts

## Licence

[MIT](LICENSE)
