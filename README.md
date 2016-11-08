# Curso de Docker

Este curso asume que en el equipo se encuentra instalado docker y docker-compose.

# Indice

* Verificar la instalación
* 


# Trabajar con imagenes

Las imagenes de docker contienen información sobre un entorno. A partir de una
imagen se pueden crear contenedores, que son instancias de la imagen.

## Imagen de prueba hello-world

```
docker run hello-world
```

## Buscar imagenes en la registry

Comando:

```
docker search ubuntu
```

Output:

```
NAME                              DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
ubuntu                            Ubuntu is a Debian-based Linux operating s...   5002      [OK]       
ubuntu-upstart                    Upstart is an event-based replacement for ...   68        [OK]       
rastasheep/ubuntu-sshd            Dockerized SSH service, built on top of of...   47                   [OK]
ubuntu-debootstrap                debootstrap --variant=minbase --components...   28        [OK]       
consol/ubuntu-xfce-vnc            Ubuntu container with "headless" VNC sessi...   28                   [OK]
torusware/speedus-ubuntu          Always updated official Ubuntu docker imag...   27                   [OK]
ioft/armhf-ubuntu                 [ABR] Ubuntu Docker images for the ARMv7(a...   19                   [OK]
nickistre/ubuntu-lamp             LAMP server on Ubuntu                           10                   [OK]
nuagebec/ubuntu                   Simple always updated Ubuntu docker images...   9                    [OK]
nickistre/ubuntu-lamp-wordpress   LAMP on Ubuntu with wp-cli installed            7                    [OK]
nimmis/ubuntu                     This is a docker images different LTS vers...   5                    [OK]
maxexcloo/ubuntu                  Base image built on Ubuntu with init, Supe...   2                    [OK]
darksheer/ubuntu                  Base Ubuntu Image -- Updated hourly             1                    [OK]
admiringworm/ubuntu               Base ubuntu images based on the official u...   1                    [OK]
jordi/ubuntu                      Ubuntu Base Image                               1                    [OK]
lynxtp/ubuntu                     https://github.com/lynxtp/docker-ubuntu         0                    [OK]
labengine/ubuntu                  Images base ubuntu                              0                    [OK]
datenbetrieb/ubuntu               custom flavor of the official ubuntu base ...   0                    [OK]
teamrock/ubuntu                   TeamRock's Ubuntu image configured with AW...   0                    [OK]
esycat/ubuntu                     Ubuntu LTS                                      0                    [OK]
konstruktoid/ubuntu               Ubuntu base image                               0                    [OK]
vcatechnology/ubuntu              A Ubuntu image that is updated daily            0                    [OK]
ustclug/ubuntu                    ubuntu image for docker with USTC mirror        0                    [OK]
widerplan/ubuntu                  Our basic Ubuntu images.                        0                    [OK]
webhippie/ubuntu                  Docker images for ubuntu                        0                    [OK]
```

## Ejecutar un contenedor

```
docker run ubuntu:14.04
docker ps -a
docker run -it ubuntu:14.04 bash
```

## Armando una imagen propia

```
mkdir myBuild
cd myBuild
vim Dockerfile
```

Contenido del Dockerfile

```
FROM ubuntu:14.04
RUN apt-get -y update && apt-get install -y fortunes
CMD /usr/games/fortune -a | echo
```

