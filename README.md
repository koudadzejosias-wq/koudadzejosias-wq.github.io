# Josias Koudadze | Blog & Portfolio

Site personnel de Koudadze Kodjogan Josias, construit avec Jekyll et le thème [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy).

## Déploiement sur GitHub Pages

1. Créer un dépôt public nommé `koudadzejosias-wq.github.io` sur GitHub.
2. Placer ces fichiers à la racine du dépôt et pousser la branche `main` :

   ```bash
   git init
   git add .
   git commit -m "Initialise le portfolio Chirpy"
   git branch -M main
   git remote add origin https://github.com/koudadzejosias-wq/koudadzejosias-wq.github.io.git
   git push -u origin main
   ```

3. Dans GitHub, ouvrir **Settings > Pages**.
4. Dans **Build and deployment**, choisir **GitHub Actions** comme source.
5. Vérifier l'exécution de l'action **Deploy Jekyll site to GitHub Pages** dans l'onglet **Actions**.
6. Le site sera disponible à l'adresse `https://koudadzejosias-wq.github.io` après le premier déploiement.

Le workflow `.github/workflows/pages-deploy.yml` reconstruit automatiquement le site à chaque push sur `main`. Il utilise le mode Pages officiel avec un artefact `_site`.

## Prévisualisation locale

Installer Ruby et Bundler, puis lancer :

```bash
bundle install
bundle exec jekyll serve --livereload
```

Ouvrir ensuite `http://127.0.0.1:4000`.

## Personnalisation

- Modifier l'identité et les liens dans `_config.yml`.
- Modifier la bio dans `_tabs/about.md`.
- Ajouter des articles dans `_posts/` avec le format `YYYY-MM-DD-titre.md`.
- Ajouter les réalisations dans `_tabs/achievements.md`.
- Ajouter les projets dans `_tabs/projects.md`.
- Remplacer les URLs d'images distantes des articles par des fichiers locaux dans `assets/img/` si souhaité.
