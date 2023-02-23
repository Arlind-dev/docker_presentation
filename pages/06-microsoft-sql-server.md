# Microsoft SQL Server mit persistent storage

### Was ist persistent storage? bzw. Volumes

Docker Volumes sind eine Möglichkeit, Daten zwischen dem Computer und einem Docker-Container auszutauschen. Sie ermöglichen es, Daten dauerhaft zu speichern und zwischen verschiedenen Containern zu teilen.

z.B.

```yml
    volumes:
      - /Pfad/auf/deinem/Computer:/Pfad/auf/deinem/Container
```

Dadurch kann ich Container löschen und neu aufsetzen ohne, dass dieser die Daten verliert.
