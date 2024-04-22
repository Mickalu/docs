Si jamais on a un champ où on est pas certain de l'avoir on peut faire :
```
user?.name 
```

On peut dire "Si jamais on a pas cette valeur alors mettre cela" en faisant : 
```
user?.name ?? 'Anonyme'
```

Dans ces cas là alors si user n'a pas de name on aura la valeur "Anonyme"

