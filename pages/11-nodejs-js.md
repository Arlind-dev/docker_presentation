# Node.js-Server, der sich mit der MSSQL-Datenbank verbindet

### index.js

```js {-} {maxHeight:'350px'}
const sql = require('mssql');
const express = require('express');
const app = express();

// SQL Server configuration
const config = {
  user: 'sa',
  password: 'arlind123',
  server: 'mssql',
  database: 'testdb',
  options: {
    encrypt: true,
    trustServerCertificate: true
  },
  retry: {
    max: 10,
    delay: 5000
  }
};

// Define a function to retrieve data from a table
async function getTableData(tableName) {
  const pool = await sql.connect(config);
  const result = await pool.request().query(`SELECT * FROM ${tableName}`);
  return result.recordset;
}

// Define an endpoint to retrieve data from all tables
app.get('/', async (req, res) => {
  try {
    const pool = await sql.connect(config);
    const tableNames = await getTableData('INFORMATION_SCHEMA.TABLES');
    const data = {};
    for (let i = 0; i < tableNames.length; i++) {
      const tableName = tableNames[i].TABLE_NAME;
      const tableData = await getTableData(tableName);
      data[tableName] = tableData;
    }
    res.json(data);
  } catch (err) {
    console.error(err);
    res.status(500).send('Error retrieving data from SQL Server');
  }
});

// Start the server
app.listen(3000, () => console.log('Server running on port 3000'));
```
