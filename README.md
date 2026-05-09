# Template - Site academique Quarto (maitrise/doctorat en kinesiologie)

Template pret a utiliser pour creer un site personnel d'etudiante/etudiant chercheur et le deployer sur Posit Connect Cloud.

## Ce que contient le template

- `index.qmd` : page d'accueil
- `profil.qmd` : profil academique
- `recherche/` : projets et travaux de recherche
- `enseignement/` : experiences d'enseignement
- `conferences/` : conferences/communications
- `gabarits/` : modeles `.qmd` a copier

## Principe important: ajout automatique des pages

Les pages `recherche/index.qmd`, `enseignement/index.qmd` et `conferences/index.qmd` utilisent des **listings**.

Si vous ajoutez un fichier `.qmd` dans les dossiers ci-dessous, il apparaitra automatiquement dans la section correspondante:

- `recherche/elements/`
- `enseignement/elements/`
- `conferences/elements/`

## Demarrage rapide

1. Creez un repo GitHub a partir de ce template.
2. Clonez le repo localement.
3. Ouvrez le projet dans RStudio.
4. Modifiez `index.qmd` et `profil.qmd` avec vos infos.
5. Lancez `quarto preview` pour voir le site.

## Ajouter un nouvel element

Exemple (nouveau projet de recherche):

1. Copiez `gabarits/modele-recherche.qmd`.
2. Placez la copie dans `recherche/elements/`.
3. Renommez le fichier (ex: `2026-03-10-mon-projet.qmd`).
4. Editez le contenu.

Meme logique pour:

- `gabarits/modele-enseignement.qmd` -> `enseignement/elements/`
- `gabarits/modele-conference.qmd` -> `conferences/elements/`

## Deploiement sur Posit Connect Cloud

1. Poussez votre repo sur GitHub.
2. Connectez-vous a Posit Connect Cloud.
3. Creez un nouveau contenu a partir de GitHub.
4. Selectionnez ce repo et la branche principale.
5. Deployez.

A chaque `git push`, vous pouvez relancer un redeploiement dans Connect Cloud.

## Commandes utiles

```bash
quarto preview   # apercu local
quarto render    # rendu complet
```

## Commande finito (sauvegarde Git simplifiee)

Une commande `finito` est fournie a la racine du projet pour les etudiantes/etudiants qui ne veulent pas gerer Git manuellement.

Ce que fait `finito`:
- verifie que vous etes bien dans un repo Git sur la branche `main`
- fait un `pull --rebase --autostash` defensif
- ajoute tous les fichiers modifies
- cree un commit avec un message fixe
- pousse sur `origin/main`

Utilisation:

```bash
bash finito
```

Si vous etes sur macOS/Linux (ou Git Bash) et que le fichier est executable:

```bash
./finito
```
