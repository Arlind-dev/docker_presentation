# Docker Umgebung erstellen

Da wir Docker nun installiert haben, können wir Portainer mithilfe der folgenden `docker-compose.yml`-Datei installieren:

```yml
version: "3.8" # Gibt die Version des Docker-Compose-Dateiformats bzw YAML-Format an, das verwendet wird.
services: # Definiert die Docker-Services, die von Docker Compose erstellt und verwaltet werden sollen.
  portainer: # Der Name des definierten Services.
    container_name: portainer # Container name
    hostname: portainer
    image: portainer/portainer-ce:latest # Gibt das Portainer Image an
    ports:
      - 9443:9443 # Ordnet Port 9443 auf der Host-Maschine dem Port 9443 im Container zu.
    volumes: # Gibt Volumes an, die im Container gemountet werden sollen.
      - /home/arlind/docker/container/portainer:/data # Host /home/arlind/docker/container/portainer -> Container /data
      - /var/run/docker.sock:/var/run/docker.sock # Host docker socket -> Container docker socket
    restart: unless-stopped # Der Container wird immer neustarten ausser er wird manuel gestoppt.
volumes:
  data:
```

Dies kann mit dem folgenden Befehl ausgeführt werden:

```bash
docker compose up -d
```
