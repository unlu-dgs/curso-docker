# Utilizando Data Volumes

Cualquier cambio realizado dentro de un contenedor y que no sea incluido en la
build del mismo no es persistido al detenerse el contenedor.

Tenemos entonces 2 posibilidades para persistir cambios:

* Si los cambios son de configuracion o infraestructura -> Dockerfile y run
* Si son datos de la aplicacion (Una base de datos, como caso tipico)

Para este ultimo caso, Docker propone el uso de Data Volumes

## Uso basico de Data Volumes

Reutilizando la imagen de apache, cargar codigo propio que sea ejecutado por
el web server.

```
mkdir myApp
vim info.html
```

Ingresar algo de codigo html propio

```
<html>
 <head>
	<title>Desde un DataVolume</title>
 </head>
 <body>
	<h1>Hola Mundo</h1>
 </body>
</html>
```

Ahora falta 'decirle' al container que use el directorio como DV

```
docker run -d -p 8080:80 -v /path/directorio/local/myApp:/var/www/html/myApp  <username>/<repository_name>:<tag>
```


