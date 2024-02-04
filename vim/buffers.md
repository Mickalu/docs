# Buffers

Les buffers sont une représentations d'un fichier. On peut dire que ce sont un 
visuel d'un fichier. On peut avoir le même buffer plusieurs fois dans une même
fenêtre sans problème. 

Voici des commandes de basess afin de gérer les buffers. 

get list buffers :
```
:buffers

or 

:ls
```

Une description de ce que les icônes devant les buffers :
```
        u       Buffer is unlisted |unlisted-buffer|.
         %      Current buffer.
         #      Alternate buffer.
          a     Buffer is loaded and displayed.
          h     Buffer is loaded but hidden.
           =    Buffer is read-only.
           -    Buffer is not modifiable, the 'modifiable' option is off.
            +   Buffer has been modified.
```

Pour éditer un buffer on peut utiliser la commande :
```
:buffer 2
```

2 étant le numéro du buffer

On peut utiliser aussi le nom du buffer si on veut l'éditer au lieu du numéro. 

On peut aussi ouvrir un buffer dans une autre fenêtre avec la commande :
```
:sbuffer 2
```

On peut aussi passer de buffer en buffer plus rapidement avec ces commandes : 
```
        :bnext          go to next buffer
        :bprevious      go to previous buffer
        :bfirst         go to the first buffer
        :blast          go to the last buffer
```

et pour supprimer un buffer on peut faire :
```
:bdelete 2
```
