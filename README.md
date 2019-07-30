# Docker WordPress

Instala rápidamente un ambiente de desarrollo local para trabajar con [WordPress](https://es.wordpress.org/) utilizando [Docker](https://www.docker.com). 

Este proyecto ofrece una instalación rápida, con versiones estandar y con la mínima cantidad de modificaciones a las imágenes de Docker. Viene configurado con  `PHP 7.3`, `MySQL 5.7` y la última versión de WordPress.

### Requerimientos

* [Docker Desktop](https://www.docker.com/products/docker-desktop)
* [WP-CLI](https://wp-cli.org/)

### Configurar el ambiente de desarrollo

Puedes utilizar la configuración por defecto, pero en ocasiones es recomendable modificar la configuración para que sea igual al servidor de producción. La configuración se ubica en el archivo `.env` con las siguientes opciones:

* `PHP_VERSION` versión de PHP ([Versiones disponibles de PHP](https://github.com/docker-library/docs/blob/master/php/README.md#supported-tags-and-respective-dockerfile-links)).
* `PHP_PORT` puerto para servidor web.
* `MYSQL_VERSION` versión de MySQL([Versiones disponibles de MySQL](https://hub.docker.com/_/mysql)).
* `MYSQL_USER` nombre de usuario para conectarse a MySQL.
* `MYSQL_PASSWORD` clave de acceso para conectarse a MySQL.
* `MYSQL_DATABASE` nombre de la base de datos que se crea por defecto.

### Instalar el ambiente de desarrollo

La instalación se hace en línea de comandos:

```zsh
docker-compose up -d
```
### Instalar WordPress

Utilizamos `wp-cli` para descargar WordPress (En la última versión y en inglés):

```zsh
wp core download
```

Si prefieres puedes instalar WordPress en Español:

```zsh
wp core download --locale=es_ES
```

También puedes instalar Wordpress en Español y con una versión especifica:

```zsh
wp core download --locale=es_ES --version=4.8.8
```

Finalmente se completa la instalación siguiendo los pasos de la siguiente ruta: [http://localhost/](http://localhost/)

### Comandos disponibles

Una vez instalado, se pueden utilizar los siguiente comandos:

```zsh
docker-compose start    # Iniciar el ambiente de desarrollo
docker-compose stop     # Detener el ambiente de desarrollo
docker-compose down     # Detener y eliminar el ambiente de desarrollo.
```

### Estructura de Archivos

* `/docker/` contiene los archivos de configuración de Docker.
* `/www/` carpeta para los archivos PHP de WordPress.

### Accesos

| Servicio | Dominio  | Usuario | Clave |
|---|---|---|---|
| MySQL | mysql | wordpress | password |
| Web | http://localhost/ | | |
| Admin | http://localhost/wp-admin/ |  |  |
