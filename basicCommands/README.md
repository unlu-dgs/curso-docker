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

## Build de una imagen

Una vez creado el archivo `Dockerfile`, se procede a construir una imagen nueva

```
docker build -t fortune-test .
```

Una vez finalizada la construcción, se puede usar la nueva imagen para 
levantar contenedores. Para usar la build construida en el paso anterior:

```
docker run -t fortune-test
```

## Imagenes locales

Una vez que se comienza a trabajar con docker, puede resultar de interes
conocer que imagenes se tienen descargadas de forma local.

```
docker images
```

## Consola interactiva al contenedor

Si bien no es recomendable ni necesario, muchas veces puede resultar 
conveniente loguearse al contenedor tal como lo hariamos con una VM o
un server. Para lograr eso se puede ejecutar el siguiente comando:

```
docker run -t -i fortune-test /bin/bash
```

## Demonizar un contenedor

Forma basica de que un contenedor quede corriendo haciendo "algo"

```
docker run -d ubuntu /bin/sh -c "while true; do echo hello world; sleep 1; done"
docker ps
docker logs <NAME_COLUMN>
docker top <NAME_COLUMN>
docker stop <NAME_COLUMN>
docker start <NAME_COLUMN>
docker stop <NAME_COLUMN>
docker rm <NAME_COLUMN>
```


