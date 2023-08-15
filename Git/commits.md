# Ajouter des éléments

Pour ajouter des éléments il faut faire la commande : 

```bash
git add .
```

À la suite du add il faut noter ce que l’on veut ajouter. Le ‘.’ lui permet d’ajouter tous les fichiers qui ont été modifier mais vous pouvez préciser ceux que vous voulez ajouter comme via cet exemple où on ajoute seulement les fichier python : 

```bash
git add *.py
```

# Le commit

Pour faire un commit vous pouvez utiliser :

```bash
git commit -m "first commit"
```

## Modifier le dernier commit

Il est possible de modifier le dernier commit, par exemple, changer le dernier message de ce dernier. 

Pour faire cela il faut utiliser **amend.** Amend a de multiple moyen de modifier le dernier commit. 

Pour changer le message on fait 

```bash
git commit --amend -m "new message"
```
