# Beginning

Pour mettre son repo sur sa machine locale on peut faire la commande

```bash
git remote add origin url_repo
```

# Fetch

Il y a un truc qui va changer maintenant c’est que nous allons avoir besoin de récupérer les changements qu’il y a en ligne. Pour cela il y a la commande.

```bash
git fetch
```

Qui va nous permettre de voir si il y a des changements qui ont été faites sur le server en ligne.

Pour voir la différence on peut faire :

```bash
git diff
```

### Merge

De cela on va ensuite merge ce qu’il y a en ligne sur notre locale en faisant 

```bash
git merge origin/master
```

# Pull

Pour faire tout cela de façon bien plus rapide on peut faire la commande 

```bash
git pull
```

On peut pull d’une branch en remote 

```bash
git pull origin <nom_branch>
```

il est aussi possible de pull avec une destination

```bash
git pull origin main:feature
```

On va alors prendre les infos de la branch en remote **main** et les mettre dans la branche **feature.**

## Les branches remotes et locals

Il y a deux types de branches, celle qui sont en local et en remote (donc accessible en ligne sur github) et celle que en locale (donc pas sur github). 

**Pour voir les branches en remote et en local on fait :**

```bash
git branch -a
```

**Pur avoir que les branches remote :**

```bash
git branch -r
```

### Push une branch en remote

```bash
git push origin <name_branch>
```

Pour la suite des push on peut automatiser le faîte de faire nos push directement sur le remote avec la commande 

```bash
git push --set-upstream origin <nom_branch>
```

[Contribution](https://www.notion.so/Contribution-c8f3f761219e44f38bd02b95fbe100ea?pvs=21)
