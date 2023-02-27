# Microsoft SQL Server mit persistent storage

### Was ist persistent storage? bzw. Volumes

Docker Volumes sind eine Möglichkeit, Daten zwischen dem Computer und einem Docker-Container auszutauschen. Sie ermöglichen es, Daten dauerhaft zu speichern und zwischen verschiedenen Containern zu teilen.

z.B.

```yml
    volumes:
      - /Pfad/auf/deinem/Computer:/Pfad/auf/deinem/Container
```

Dadurch können Container gelöscht und neu aufgesetzt werden, ohne dass die Daten verloren gehen.
