# Node.js-Server, der sich mit der MSSQL-Datenbank verbindet

Wir werden jetzt 2 Docker-Container erstellen, die einen Netzwerkadapter teilen, damit sie miteinander kommunizieren können.

1. Container 1 wird ein Microsoft SQL Server sein, mit einer Datenbank namens testdb.
2. Container 2 wird ein Node.js-Container sein, der sich mit dem Microsoft SQL Server vom ersten Container verbindet und die Daten als JSON ausgibt.

Bevor wir starten können, müssen wir zuerst unsere Node.js-Umgebung erstellen, dort wo der Docker-Container gemounted wird. In meinem Fall habe ich mich für /home/arlind/docker/container/node entschieden.

Dies können wir mit den folgenden Schritten erreichen:

1. `mkdir -p /home/arlind/docker/container/node` (Erstellt den Ordner)
2. `npm init` (Initialisiert das Node.js-Projekt)
3. `npm install (modules)` (Installiert die benötigten Node-Module)
4. `nano index.js` (Erstellt und öffnet die index.js-Datei zum Bearbeiten)
