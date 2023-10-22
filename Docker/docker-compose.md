# Docker-compose

Docker-compose is here to manage multiple docker between them.
It's pretty commun to have a front app and a back app in web devlopment.  

Pour commencer il faut créer un fichier en .yml comme ceci :

``` text
docker-compose.yml
```

Ce fichier va initialiser les différents env qu'il y aura dans notre container et définira comment ces derniers communiqueront.

Voici un exemple à quoi cela peut ressembler :

``` yml
version: "3"

services:
  app:
    build:
      context: .
      args:
        - REACT_APP_API_URL=http://localhost
    ports:
      - "80:80"
    volumes:
      - .:/app
    networks:
      - appli_network

networks:
   appli_network:
    external: true

```

On va y aller point par point afin de comprendre ce que fait ce fichier.

## version

La version est la version de notre app

## services

link [https://docs.docker.com/compose/compose-file/05-services/]

La section **services** permet de lister l'ensemble des services de notre container.
Ici on a le service app. Mais on peut mettre plusieurs services à la suite car ce sont ceux qui vont communiquer dans notre container.

Notre premier service s'appelle ***app***. C'est notre application react ici.

### build

Build va nous permettre de configurer comment notre application se lance.
Ici on a mit des variables d'env qui seront utilisé dans notre application.
Ces variables seront récupérées dans le Dockerfile comme ceci :

``` Dockerfile
ARG REACT_APP_API_URL
ENV REACT_APP_API_URL=$REACT_APP_API_URL
```

Ici c4est l'URL de notre api.
