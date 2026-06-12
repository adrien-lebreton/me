# me — ⚠️ Sortie de build (NE PAS ÉDITER ICI)

Ce dépôt contient **uniquement le code compilé** de mon portfolio Angular, servi par GitHub Pages.

- 🔗 **Site en ligne** : https://adrien-lebreton.github.io/me/
- 📦 **Code source (développement)** : 👉 **https://github.com/adrien-lebreton/me-source** 👈

## Ne rien modifier ici

Les fichiers de ce repo (`main.*.js`, `polyfills.*.js`, `runtime.*.js`, `styles.*.css`,
`ngsw-worker.js`, images hashées, etc.) sont **générés automatiquement** par
`ng build --configuration production` depuis le repo
[`me-source`](https://github.com/adrien-lebreton/me-source).

➡️ Toute modification faite directement ici sera **écrasée au prochain build**.
Le vrai développement se fait dans [`me-source`](https://github.com/adrien-lebreton/me-source).

## Comment c'est déployé

1. Développer dans [`me-source`](https://github.com/adrien-lebreton/me-source) (Angular 13 / JHipster).
2. Builder : `npm run webapp:prod` → sortie dans `target/classes/static/`.
3. Copier le **contenu** de `target/classes/static/` à la racine de **ce** repo.
4. `git commit` + `git push` sur `main` → GitHub Pages republie automatiquement.

> ℹ️ Le site est servi sous le chemin `/me/` (project page), d'où le `<base href="/me/">`
> dans `index.html`. Renommer ce repo casserait l'URL — à éviter.
