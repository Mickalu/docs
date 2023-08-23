# Docker 

## Build new image

We need to create a Dockerfile like that 
```
FROM node:18-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000
```
This Dockerfile is for a Node.js app.

### multiple docker
Il est possible d'avoir plusieurs fichiers Dockerfile dans un même projet afin de pouvoir lancer notre app de façon différente. Exemple si nous voulions un fichier Dockerfile de production et un autre de dev. 
Pour cela il faut créer un autre fichier dockerfile avec un nom différent comme par exemple :
```
Dockerfile.dev
```

For running this file use this command : 
```
docker build -f Dockerfile.dev .
```


For build this i;age we need to use the command : 
```
docker build -t getting-started .
```

FROM node:18-alpine is the image and docker need to download it.
CMD ["node", "src/index.js"] command is the command which run the app.

***-t *** permit to add a name at the image 

## Start an app container 
for running the container we can use this command : 

```
docker run -dp 127.0.0.1:3000:3000 getting-started
```
```-d``` say to run the container in the background.
```-p``` create a port between host and container

This command will stop the container
```
docker stop container_name
```


## Update source code 
```
docker run -dp 127.0.0.1:3000:3000 getting-started
```
