Il est possible via git de trouver simplement une erreur via la commande 

```bash
git bisect 
```

elle va nous permettre de dire si un commit est bon et si un autre est mauvais. Le commit qui a créer un bug se trouve forcément entre les deux, donc git va nous bouger pour savoir où est l’erreur. 

On va définit un commit dont on est certain qu’il est mauvais (ici on défini où on est): 

```bash
git bisect bad 
```

Ensuite il faut définir un commit qui est bon (on va prendre le premier commit de la branch)

Avoir le premier commit de la branch : 

```bash
git log --oneline | tail -n 1
```

On obtient le code du premier commit (ici f0ea950), on fait maintenant : 

```bash
git bisect good f0ea950
```

Ensuite git va nous checkout de commit en commit entre ces deux commit et on va définir si ce sont de bon commit ou non avec les commandes : 

```bash
git bisect good
git bisect bad 
```

À la fin git va trouver le mauvais commit et nous donner toutes les informations de ce dernier : 

```bash
326f68a558501a6f44d7685c2c1795794bac09b5 is the first bad commit
commit 326f68a558501a6f44d7685c2c1795794bac09b5
Author: Radovan Bast <bast@users.noreply.github.com>
Date:   Fri Mar 29 16:02:52 2019 +0100

    commit number 137

 get_pi.py | 8 ++++----
 1 file changed, 4 insertions(+), 4 deletions(-)
```
