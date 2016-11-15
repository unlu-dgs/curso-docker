# Creando imagenes personalizadas

Una de las caracteristicas mas utiles de Docker es el uso de imagenes creadas
por otros para crear imagenes propias editando una minima cantidad de cosas de
la imagen base.

Veamos las imagenes que tenemos descargadas

```
docker images
```

Deberiamos tener una imagen `ubuntu:<version-number>`

Vamos a instalar un servicio, hacer una build de dicho contenedor, pero tambien
crear una imagen para no tener que hacer la build si queremos reutilizar, o
queremos compartir nuestra imagen con otros desarrolladores (Posiblemente 
dentro del mismo equipo de trabajo, aunque no limitado).

## Construyendo una imagen que ejecuta un servicio

En el archivo `Dockerfile.apache` se encuentra una forma basica de crear un
contenedor que ejecute un servicio.

El objetivo sera crear una build y subirla a la registry de docker con un
usuario creado en el sitio[1].

### Creando el Dockerfile

* Crear una carpeta vacia
* Copiar el archivo (Dockerfile.apache)[/basicCommands/Dockerfile.apache] 
con el nombre `Dockerfile`

### Registrando en la registry

* Crearse un usuario en [1]
* Loguearse en la cuenta con el comando `docker login`
* Crear un nuevo repositorio

### Build & Push

* Creamos una build 

```
docker build . -t <username>/<repository_name>:<tag>
```

Donde:
 * <username> es el nombre de usuario creado en la registry
 * <repository_name> nombre del repositorio creado con la registry
 * <tag> es el numero de version de la build, nos permite versionar la imagen

* Subir la imagen a la registry 

```
docker push <username>/<repository_name>:<tag>
```









# Referencias

[1]: https://hub.docker.com/
