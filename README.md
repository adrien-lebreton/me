# me — ⚠️ Sortie de build (NE PAS ÉDITER ICI)

Ce dépôt contient **uniquement le code compilé** de mon portfolio Angular, servi par GitHub Pages.

- 🔗 **Site en ligne** : https://adrien-lebreton.github.io/me/
- 📦 **Code source (développement)** : 👉 **https://github.com/adrien-lebreton/me-source** 👈

## Ne rien modifier ici

Les fichiers de ce repo (`main-*.js`, `chunk-*.js`, `polyfills-*.js`, `styles-*.css`,
`ngsw-worker.js`, images hashées dans `media/`, pages prérendues, `sitemap.xml`, etc.) sont
**générés automatiquement** depuis le repo
[`me-source`](https://github.com/adrien-lebreton/me-source).

➡️ Toute modification faite directement ici sera **écrasée au prochain build**.
Le vrai développement se fait dans [`me-source`](https://github.com/adrien-lebreton/me-source).

## Comment c'est déployé

1. Développer dans [`me-source`](https://github.com/adrien-lebreton/me-source) (Angular 22).
2. Builder : `npm run webapp:prod:seo` → build de production, puis prérendu de chaque page
   en français (`/me/…`) et en anglais (`/me/en/…`) avec le `sitemap.xml`. Sortie dans
   `target/classes/static/`.
3. Synchroniser cette sortie avec la racine de **ce** repo (depuis `me-source`) :
   ```sh
   rsync -a --delete --exclude .git --exclude .nojekyll --exclude README.md --exclude .idea \
     target/classes/static/ ../me/
   ```
4. `git commit` + `git push` sur `main` → GitHub Pages republie automatiquement.

> ℹ️ Le site est servi sous le chemin `/me/` (project page), d'où le `<base href="/me/">`
> dans `index.html`. Renommer ce repo casserait l'URL — à éviter.
