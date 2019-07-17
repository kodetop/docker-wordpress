# Docker WordPress

Instala rápidamente un ambiente de desarrollo local para trabajar con WordPress. Viene configurado con `MySQL 5.6` y `PHP 7.2`, además viene configurado para evitar versionar los archivos de WordPress.

### Requerimientos

* [Docker Compose](https://docs.docker.com/compose/)
* [WP-CLI](https://wp-cli.org/)

### Configurar el ambiente de desarrollo

* Clonar el repositorio. 
* Instalar el contenedor Docker:
  `docker-compose up -d`
* Instalar Wordpress:
  `wp core download --path=www/ --locale=es_ES`

### Comandos disponibles

* `docker-compose start` iniciar el ambiente de desarrollo.
* `docker-compose stop` detener el ambiente de desarrollo.
* `docker-compose down` detener y eliminar el ambiente de desarrollo.

### Estructura de Archivos

* `/docker/` contiene los archivos de configuración de Docker.
* `/www/` carpeta para los archivos PHP del proyecto.

### Accesos

| Servicio | Dominio  | Usuario | Clave |
|---|---|---|---|
| MySQL | mysql | wordpress | password |
| Web | http://localhost/ | | |
| Admin | http://localhost/wp-admin/ |  |  |
