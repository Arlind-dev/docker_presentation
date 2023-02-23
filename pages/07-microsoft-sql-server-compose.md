# Microsoft SQL Server mit persistent storage

### `docker-compose.yml`

```yml
version: '3.8' # YAML Version
services: # Welche Services benutzt werden
  db: # Der Name des definierten Services.
    image: mcr.microsoft.com/mssql/server:2019-latest # Gibt das Image an, das für den Service verwendet werden soll, in diesem Fall die neueste Version von der 2019 Version
    container_name: mssql # Container name
    hostname: mssql
    user: root
    environment: # Container spezifische Einstellungen
      MSSQL_SA_PASSWORD: "arlind123" # Datenbank root passswort
      ACCEPT_EULA: "Y" # EULA annehmen
    ports:
      - "1433:1433" # Ordnet Port 1433 auf der Host-Maschine dem Port 1433 im Container zu.
    volumes:
      - /home/arlind/docker/container/sqlserver/data:/var/opt/mssql/data
      - /home/arlind/docker/container/sqlserver/logs:/var/opt/mssql/logs
      - /home/arlind/docker/container/sqlserver/secrets:/var/opt/mssql/secrets
    restart: unless-stopped # Der Container wird immer neustarten ausser er wird manuel gestoppt.
```
