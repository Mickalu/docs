# Configurer les branches

Pour définir la branche par défaut on peut faire : 

```bash
git config --global init.defaultBranch main
```

## Historique

Pour voir l’historique d’une branch on peut faire la commande 

```bash
git log
```

## Créer une nouvelle branch

Pour créer une nouvelle branch il faut faire la commande 

```bash
git checkout -b 2-faire-un-compteur
```

ça va créer une branch et ensuite switch dans cette dernière

### Faire suivre une branch

Une branche peut suivre une autre lors de la création afin que 

### Mettre en ligne

On peut ensuite la mettre en ligne en faisant 

```bash
git add .
git commit -m "first commit"
git push -u origin <nom branch>
```

# Git cherry-pick

Permet de redéfinir le HEAD de notre branch. 

# Diff Revert and Reset

**git revert** va ajouter un commit où on va revenir à un commit précédent de la branch. 

**git reset**  va quand à lui revenir à un point de commit en supprimant l’historique etc. 

## Git reflog

Git reflog permet de savoir quand des ref de notre branch ont été mis à jour et aussi voir quand. 

```bash
git reflog
```

On peut aussi voir les valeurs des HEAD de chaque commit pour savoir comment y retourner. 

```bash
eff544f HEAD@{0}: commit: migrate existing content
bf871fd HEAD@{1}: commit: Add Git Reflog outline
9a4491f HEAD@{2}: checkout: moving from main to git_reflog
9a4491f HEAD@{3}: checkout: moving from Git_Config to main
39b159a HEAD@{4}: commit: expand on git context 
9b3aa71 HEAD@{5}: commit: more color clarification
f34388b HEAD@{6}: commit: expand on color support 
9962aed HEAD@{7}: commit: a git editor -> the Git editor
```

On peut aussi voir ce qui a modifier les valeurs (genre si c’était un commit ou autre)
