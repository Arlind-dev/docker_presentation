# Node.js-Server, der sich mit der MSSQL-Datenbank verbindet

### Datenbank erstellen

Sobald wir unsere Container gestartet haben, müssen wir in der MSSQL-Datenbank noch eine Datenbank mit einer Tabelle und Inserts erstellen.

Hierfür können wir folgende Schritte ausführen:

<div grid="~ cols-2 gap-4">

<div>

```bash
docker exec -it mssql /bin/bash
```
<br>
```bash
/opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P 'arlind123'
```

<br>
```sql
CREATE DATABASE testdb;
GO

USE testdb;
GO
```

</div>
<div>


```sql
CREATE TABLE TEST (
  id INT,
  name VARCHAR(255),
  age INT
);


INSERT INTO TEST (id, name, age)
VALUES
(1, 'Nathan', 15),
(2, 'Harun', 16),
(3, 'Fran', 17),
(4, 'Arlind', 18);
```
</div>
</div>
