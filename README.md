# Kiraku Travel — Page « bientôt » (déploiement)

Dossier **prêt à mettre sur GitHub puis Hostinger**. Léger (~1 Mo), il ne contient QUE la page d'attente et ses ressources — aucune image source, `.docx` ni `.pdf`.

```
index.html              ← page d'accueil
colors_and_type.css     ← charte (couleurs, typo)
assets/                 ← sceau hanko + mot-symbole
fonts/                  ← Shippori Mincho (woff2 optimisé, graisses 500/600)
.htaccess               ← config Hostinger (cache, compression, HTTPS)
```

## Mettre sur GitHub (dépôt `japonautrement`)

Le glisser-déposer web de GitHub refuse les fichiers > 25 Mo. Ce dossier est léger, donc tu peux :

**Option 1 — glisser-déposer web :** ouvre le dépôt `japonautrement` → « Add file → Upload files » → dépose le **contenu de ce dossier** (pas le dossier parent) → Commit. Crée bien la branche `main`.

**Option 2 — en ligne de commande (recommandé) :**
```bash
cd "kiraku-bientot"
git init
git add .
git commit -m "Page bientot Kiraku Travel"
git branch -M main
git remote add origin https://github.com/diops-dev/japonautrement.git
git push -u origin main
```

## Déployer sur Hostinger (Git natif)

hPanel → **Avancé → Git** (ou « Deploy from GitHub ») :
- Repository : `japonautrement`
- Branch : **`main`** (apparaît après le push)
- Deploys to : `public_html`
- Clique **Deploy**.

La page sera en ligne sur `japonautrement.fr`.

## À faire avant la prod
- Remplacer l'e-mail `voyage@japonautrement.fr` dans `index.html` si besoin.
- Activer le bloc « Forcer HTTPS » dans `.htaccess` une fois le SSL Hostinger actif.
