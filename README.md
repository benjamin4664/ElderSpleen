# Elders Spleen — site

Site statique, sans dépendance, sans étape de build. Juste du HTML/CSS.

## Structure

```
index.html              → page d'accueil
css/style.css            → tout le style du site
blog/index.html           → liste des articles
blog/posts/*.html         → chaque article
blog/posts/_template.html → gabarit à copier pour un nouvel article
```

## Ajouter un article

1. Copier `blog/posts/_template.html` sous un nouveau nom, ex. `blog/posts/mon-article.html`.
2. Remplir titre, date, chapô, corps.
3. Ajouter une entrée correspondante en haut de `blog/index.html` ET dans la
   section "Derniers fragments" de `index.html` (copier un `<article class="fragment-item">`
   existant et l'adapter).

## Voir le site en local

Aucun serveur n'est requis : ouvrir `index.html` directement dans un navigateur.
Pour un rendu plus fidèle (chemins relatifs), on peut aussi lancer un petit serveur local :

```bash
cd elderspleen-site
python3 -m http.server 8000
# puis ouvrir http://localhost:8000
```

## Mettre le site en ligne (GitHub Pages, gratuit)

1. Créer un dépôt GitHub, ex. `elderspleen-site`.
2. Depuis ce dossier :
   ```bash
   git init
   git add .
   git commit -m "premier commit"
   git branch -M main
   git remote add origin https://github.com/<ton-compte>/elderspleen-site.git
   git push -u origin main
   ```
3. Sur GitHub : Settings → Pages → Source → choisir la branche `main` et le dossier `/ (root)`.
4. Le site sera en ligne sous `https://<ton-compte>.github.io/elderspleen-site/`.

### Nom de domaine personnalisé (optionnel)

Si tu achètes un domaine (ex. `elderspleen.com`), ajoute un fichier `CNAME`
à la racine contenant juste le domaine, et configure un enregistrement DNS
`CNAME` pointant vers `<ton-compte>.github.io`.

## Personnalisation

Toutes les couleurs et polices sont définies en haut de `css/style.css`
dans le bloc `:root { ... }` — modifier les valeurs hex là suffit à
changer toute la palette du site.
