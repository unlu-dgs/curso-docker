# Armando una imagen propia

```
mkdir myBuild
cd myBuild
vim Dockerfile
```

## Dockerfile

El archivo Dockerfile permite personalizar un contenedor, tomando de base una 
imagen y ejecutando comandos en base al objetivo que queremos lograr con el 
contenedor. 

```
FROM ubuntu:14.04

ENV http_proxy http://proxy.unlu.edu.ar:8080
ENV https_proxy http://proxy.unlu.edu.ar:8080

RUN apt-get -y update && apt-get install -y fortunes
CMD /usr/games/fortune -a | echo
```

Referencias: https://docs.docker.com/engine/reference/builder/

## Build del contenedor

Una vez creado el archivo `Dockerfile`


docker build -t fortune-test .
docker run -t fortune-test
