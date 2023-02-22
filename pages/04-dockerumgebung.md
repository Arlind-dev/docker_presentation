# Docker umgebung erstellen

### Portainer installieren

Da wir jetzt Docker installiert haben können wir jetzt Portainer installieren mit diesem <br> `docker-compose.yml`:

```yml
version: "3.8" # Gibt die Version des Docker-Compose-Dateiformats bzw YAML-Format an, das verwendet wird.
services: # Definiert die Docker-Services, die von Docker Compose erstellt und verwaltet werden sollen.
  portainer: # Der Name des definierten Services.
    image: portainer/portainer-ce:latest # Gibt das Portainer Image an
    ports:
      - 9443:9443 # Ordnet Port 9443 auf der Host-Maschine dem Port 9443 im Container zu.
    volumes: # Gibt Volumes an, die im Container gemountet werden sollen.
      - data:/data # Bindet das Daten-Volume mit dem Namen "data" an das Verzeichnis /data im Container an.
      - /var/run/docker.sock:/var/run/docker.sock # Host docker socket -> Container docker socket
    restart: unless-stopped # Der Container wird immer neustarten ausser er wird manuel gestoppt.
volumes:
  data:
```

Ausführen müssen wir dies mit:

```bash
docker compose up -d
```
