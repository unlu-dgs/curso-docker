# Armando una imagen propia

```
mkdir myBuild
cd myBuild
vim Dockerfile
```

## Dockerfile

```
FROM ubuntu:14.04
RUN apt-get -y update && apt-get install -y fortunes
CMD /usr/games/fortune -a | echo
```

Referencias: https://docs.docker.com/engine/reference/builder/

