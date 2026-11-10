# PHP2Shell · Procedimiento de actualización
## Qué hace falta

Acceso al servidor con un usuario con sudo.
Conexión a los repositorios de Ubuntu.
Una copia de seguridad o snapshot de la máquina antes de actualizar.




## Cómo saber si un servidor está parcheado

mirando la version del paquete 

dpkg -l 'php8.3*' | grep ^ii


## Cómo se parchea

Actualizar el sistema:

sudo apt update && sudo apt upgrade

Reiniciar Apache para que mod_php cargue el código nuevo:

sudo systemctl restart apache2


## Cómo se comprueba después
Volver a mirar la versión de los paquetes:

dpkg -l 'php8.3*' | grep ^ii

Comprobar que Apache está activo y que se reinició después de la actualización:

systemctl status apache2

Comprobar que la web sigue respondiendo:

curl -I http://localhost
