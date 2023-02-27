# Node.js-Server, der sich mit der MSSQL-Datenbank verbindet

docker-compose.yml
```yml {-} {maxHeight:'350px'}
version: '3.8'

networks:
  mssql-node-network:

services:
  db:
    image: mcr.microsoft.com/mssql/server:2019-latest
    networks:
      mssql-node-network:
    container_name: mssql
    hostname: mssql
    user: root
    environment:
      MSSQL_SA_PASSWORD: arlind123
      ACCEPT_EULA: Y
    ports:
      - "1433:1433"
    volumes:
      - /home/arlind/container/sqlserver/data:/var/opt/mssql/data
      - /home/arlind/container/sqlserver/logs:/var/opt/mssql/logs
      - /home/arlind/container/sqlserver/secrets:/var/opt/mssql/secrets
    restart: unless-stopped
  app:
    image: node
    networks:
      mssql-node-network:
    container_name: node
    hostname: node
    volumes:
      - /home/arlind/container/node/:/app/
    working_dir: /app
    command: node index.js
    ports:
      - "3000:3000"
```
