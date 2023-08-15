# Git repository

Pour initialiser git dans un répertoire il faut faire  : 

```bash
git init
```

### Vérifier l’état des fichiers

Regarder dans quelle branche vous êtes, quels fichiers ont été modifiés etc…

```bash
git status
```

## Tracked and untracked

Les fichiers qui ne sont pas encore dans ton repository sont untracked car on ne verra pas les changement dans le status. 

Les fichiers tracked eux sont les fichiers dans le repository

## Ajouter des fichiers

Pour ajouter des fichiers dans le **stage** on peut faire 

```bash
git add file_name
```

Pour en ajouter plusieurs 

```bash
git add --all
```

# Voir les différences dans le repository

Il peut y avoir une différence entre les fichiers **staged** (qui sont dans le add) et les fichiers sur nos fichiers locaux. On peut voir cette différence avec la commande 

```bash
git diff --staged
```

On peut aussi voir la différence entre les fichiers réels et le dernier commit avec la commande 

```bash
git diff HEAD
```

On peut voir aussi avec des retours plus loin 

```bash
git diff HEAD~nb_commits
```

# Git rebase

**git rebase** permet de redéfinir la base d’une feature, c’est à dire qu’une branch de feature s’est créée après un commit et à été dans une nouvelle branch, maintenant on peut redéfinir ce commit de base. 

Vous allez me dire, “oui mais je peux merge main dans ma branch dev et ça va faire pareil”. Alors c’est pas tout çà fait vrai car l’historique de vos commits va changer car ce merge va apparaître comme le HEAD et avec rebase vous aller juste changer la base de votre branch. 

La commande principal est 

```bash
git rebase --onto <newbase> <oldbase> <branch_name>
```

Exemple pour passer de ça 

```bash
o---o---o---o---o  main
        \
         o---o---o---o---o  featureA
              \
               o---o---o  featureB
```

à ça 

```bash
						o---o---o  featureB
          /
o---o---o---o---o  main
 \
  o---o---o---o---o  featureA
```

On fait 

```bash
git rebase --onto main featureA featureB
```

### Réaranger de façon interactive

La commande 

```bash
git rebase -i HEAD~3 
```

Nous permet de réarranger dans une autre branch les 3 commits derrières. Il est possible de ne pas prendre tous les commits dedans si jamais on veut prendre la base plus haut et en supprimer quelqu’uns.

# Log and relog

Pour observer de façon graphique les branches, les commits et autre, on peut faire : 

```bash
git log --graph -- online --decorate
```

## Git log

Il est possible avec log d’ajouter des filtres afin de ne pas se taper tous les résultats à chaque fois 

```bash
git log --after="2014-7-1"
```

On peut mettre des dates, mais on peut aussi mettre des mots comme “yesterday” etc 

### Les filtres de log

On peut filtrer par date, author, message 

```bash
git log --grep="commit"
```

Par fichier etc 

# Git reflog

Cette commande a pour fonction de nous montrer la trace des mises à jours sur la pointe des branches. 

```bash
git relog 
```

On peut regarder que sur une branch 

```bash
git reflog show otherbranch 9a4491f
```

# Fonctionnement Git

Il y a trois arborescences dans git :  *le répertoire de travail*, *l’index de staging*, *l’historique des commits.* 

# Déplacement des HEADs des branches

On peut facilement changer les **HEAD** des branches afin de revenir à un point. Si vous n’êtes pas sur la branche vous pouvez faire 

```bash
git branch -f <nom_branch> HEAD~1
```

```bash
$ git branch -f main C6 // met main sur c6

$ git checkout HEAD~1 // checkout de un en arrière 

$ git branch -f bugFix HEAD~1 // HEAD de bugFix un commit en arrière 
```

# tags

On peut mettre des tags sur les commits afin de mieux se repérer dans nos branches

```bash
git tag <nom_tag> <nom_commit>
```

# Les pours ou contre rebase et merge

rebase :

Pour :

- Rebase rend votre arbre de commits très propre puisqu'il ressemble à une ligne droite.

Contre :

- Rebase modifie l'historique (apparent) de l'arbre des commits.

# Remove files from repertory

Tout d’abord il faut clean le fichier, qu’il n’y ait pas de modification que l’on pourrait add ou autre 

```bash
git restore <file_name>
```

Ensuite on l’enlève du repertoire, des fichiers stages finalement 

```bash
git rm <file_name>
```

Si on veut que ça soit tous les fichiers d’un folder on peut aussi en précisant le nom du dossier et ça sera les mêmes commandes.
