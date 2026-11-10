# PHP2Shell · Análisis

## Qué es
Son dos vulnerabilidades del propio intérprete de PHP: CVE-2026-109618 y CVE-2026-109619. Permiten que un atacante sin autenticar ejecute código en remoto en el servidor. Las dos tienen una nota CVSS 4.0 de 9.2 (crítica). Se publicaron el 17/10 y el parche salió el 21/10. Actualizar WordPress o los plugins no lo soluciona: hay que actualizar PHP.


## Versiones afectadas y corregidas

Afectadas: todas las anteriores a las corregidas, desde PHP 5.4. Las ramas sin soporte (8.1 y anteriores) no reciben versión oficial.
Corregidas: 8.5.12, 8.4.27, 8.3.36 y 8.2.35.
Ubuntu 24.04: el parche va en el paquete 8.3.6-0ubuntu0.24.04.13. "php -v" sigue mostrando 8.3.6, así que hay que mirar la versión del paquete.


## Cómo afecta a nuestro servidor

El servidor usa Ubuntu 24.04 LTS con PHP 8.3.6 servido por Apache 2.4.58 a través de mod_php (libapache2-mod-php8.3). mod_php es una de las formas de servir PHP afectadas, así que el servidor era vulnerable mientras tuvo un paquete anterior a 8.3.6-0ubuntu0.24.04.13. Ahora todos los paquetes php8.3 están en esa versión, por lo que está parcheado.


## Qué no está afectado
El fallo está en el intérprete PHP, no en Apache, ni en la base de datos, ni en el código de la aplicación web. Actualizar la aplicación (o WordPress y sus plugins) no lo soluciona.
PHP-FPM no está instalado en el servidor, así que no hay otra vía de PHP que haya que parchear aparte.
