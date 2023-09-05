# Run docker command line 

Il y a des moments on voudrait pouvoir lancer un docker simple déjà pré-construit en une line de commande. 
Cela est possible en effet. Par exemple, dans un projet j'ai eu besoin de lancer un server de mail avec django. 
Pour faire cela j'ai utilisé la commande :
```
docker run -p 1080:1080 -p 1025:1025 maildev/maildev
```

Donc on a relier le port 1080 et 1025 puis utilisé l'image maildev qui va envoyer les mails pour nous. 

