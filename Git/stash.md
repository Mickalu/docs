## Description

**Git stash** est une commande assez puissante car elle va vous permettre de stocker ce que vous avez fait sans avoir besoin de commit/add ou autre. Si jamais vous avez besoin de changer de branch pendant que vous faîtes un truc alors c’est tout à fait possible. 

Pour commencer vous allez changer un fichier dans une branch qui a déjà un commit. Ensuite il va falloir stocker tout cela dans le stash. Vous allez faire la commande 

```bash
git stash -p 
```

Vos changements se trouvent maintenant dans le stage et vous pouvez les remettre dans vos fichiers si vous les avez perdus. Comme exemple si vous changez de branche et que vous revenez alors vos changements non commite ou non add vont disparaître. 

Le réflexe est de faire 

```bash
git stash list 
// ou 
git stash show
```

Pour voir si vous avez des stashs en attente puis vous pouvez faire 

```bash
git stage apply 
```

On peut aussi utiliser 

```bash
git stash pop
```

cela fait la même chose que apply juste c’est moins long à utiliser.

Pour rétablir vos changements.

Après pour supprimer les stashs 

```bash
git stash drop // on peut spécifier quelle stash supp
git stash clear // fait la meme chose mais ne peut pas spécifier je crois
```
