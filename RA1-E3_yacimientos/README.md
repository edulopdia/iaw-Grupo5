# Mapa vivo de Butarque · capa Yacimientos
## Para qué sirve
Mapa del barrio de Butarque con 21 lugares en 5 capas y un panel para editarlos.
Mi capa: Yacimientos arqueológicos y vestigios históricos (5 lugares).
## Qué hace falta
- Un servidor con Ubuntu Server 24.04 e Internet.
- Docker y Docker Compose:
sudo apt install -y docker.io docker-compose-v2 docker-buildx unzip
- El fichero mapa-vivo-butarque.zip
## Cómo se levanta
1. unzip mapa-vivo-butarque.zip
2. cd mapa-vivo-butarque
3. nano compose.yaml (cambiar ADMIN_TOKEN por una clave propia)
4. sudo docker compose up -d --build
## Cómo se comprueba que funciona
- sudo docker compose ps -> Up (healthy)
- curl -s http://localhost:8090/api/salud -> {"estado":"ok","puntos":21}
- En el navegador: http://IP-DEL-SERVIDOR:8090 (mapa) y /admin/ (panel)
## Problemas que tuve
- La instalación de Docker se quedó parada en el 90 % unos minutos: esperé.
