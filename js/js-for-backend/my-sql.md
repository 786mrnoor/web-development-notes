# MySQL with Node.js

`MySQL2` client for Node.js with focus on performance. Supports **prepared statements**, **promise** and much more.

## 📦 1. Install `MySQL2` Package

```bash
npm install mysql2
```
---

## 🛠️ 2. Create MySQL Connection

```js
// db.js
const mysql = require('mysql2');

// Create connection
const connection = mysql.createConnection({
  host: 'localhost',     // or your DB host
  user: 'root',          // your DB username
  password: '',          // your DB password
  database: 'testdb',    // your DB name
});

// Connect
connection.connect((err) => {
  if (err) {
    console.error('❌ Error connecting: ' + err.stack);
    return;
  }
  console.log('✅ Connected as id ' + connection.threadId);
});

module.exports = connection;
```

However, a connection can also be implicitly established by invoking a query:

---

## 📄 3. Run a Basic Query

```js
// query.js
const db = require('./db');

// SELECT Query
db.query('SELECT * FROM users', (err, results) => {
  if (err) {
    console.error('❌ Query Error:', err);
    return;
  }
  console.log('📊 Query Results:', results);
});
```

---

## 💾 4. Insert Data (Safe with Prepared Statements)
Prepared Statements are SQL queries that are precompiled by the database and executed later with user-supplied values. This protects against SQL injection attacks and improves performance for repeated queries.

```js
const name = 'Ali';
const email = 'ali@example.com';

db.execute(
  'INSERT INTO users (name, email) VALUES (?, ?)',
  [name, email],
  (err, results) => {
    if (err) throw err;
    console.log('✅ Inserted ID:', results.insertId);
  }
);
```

---

## 🆕 Use Promises Instead of Callbacks

```js
// db-promise.js
const mysql = require('mysql2/promise');

async function connectDB() {
  const connection = await mysql.createConnection({
    host: 'localhost',
    user: 'root',
    password: '',
    database: 'testdb',
  });

  const [rows] = await connection.execute('SELECT * FROM users');
  console.log('Results:', rows);
}

connectDB();
```

---

## 5. Connection Pool in mysql2
A Connection Pool is a cache of reusable database connections that your application can use instead of creating a new connection every time.

```js
const mysql = require('mysql2');

const pool = mysql.createPool({
  host: 'localhost',
  user: 'root',
  password: '',
  database: 'testdb',
  waitForConnections: true,
  connectionLimit: 10,     // max number of connections
  queueLimit: 0            // unlimited queued requests
});

pool.query('SELECT * FROM users', (err, results) => {
  if (err) throw err;
  console.log(results);
});
```

**With Promises**

```js
const pool = mysql.createPool({
  // config
}).promise(); // <- Add .promise()

async function getUsers() {
  const [rows] = await pool.query('SELECT * FROM users');
  console.log(rows);
}
```


## ✅ Summary

| Task              | Code Sample                                         |
| ----------------- | --------------------------------------------------- |
| Install package   | `npm install mysql2`                                |
| Create connection | `mysql.createConnection({...})`                     |
| Run query         | `connection.query('SELECT * FROM users', callback)` |
| Use placeholders  | `'INSERT INTO users VALUES (?, ?)', [val1, val2]`   |
| Use promises      | `mysql2/promise` for async/await                    |