# Incidencias
## 1 · PHP2Shell (21/10)
# Incidencias

## 1 · PHP2Shell (21/10)

Qué pasaba: El 21/10 salió el parche de PHP2Shell (CVE-2026-109618 y CVE-2026-109619), un fallo de PHP que permite ejecutar código en remoto sin autenticación. Nuestro servidor que es un Ubuntu 24.04, Apache + mod_php tenía el paquete vulnerable `8.3.6-0ubuntu0.24.04.11`.

Causa:El fallo está en el intérprete PHP, y el servidor no se actualizó hasta el 27/10.

Solución:
El 27/10 se actualizó PHP a `8.3.6-0ubuntu0.24.04.13` con `apt upgrade` y se reinició Apache.

Comprobación: `dpkg -l 'php8.3*'` muestra la versión  y `systemctl show apache2` confirma que Apache arrancó después de la actualización.
