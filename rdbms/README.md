# 🛣️ RDBMS Learning Roadmap

## 1. **Basics of Databases**
- [What is a database?](basics/database.md)
- [What is RDBMS?](basics/rdbms.md)
- [Tables, Rows, Columns](basics/tables-rows-columns.md)
- [Primary Key and Foreign Key](basics/primary-foreign-key.md)

---

## 2. **SQL Basics**
- [**DDL (Data Definition Language)**](sql-basics/ddl.md) – Creating structure
  - `CREATE`, `ALTER`, `DROP` `TRUNCATE` `RENAME` tables
- [**DML (Data Manipulation Language)**](sql-basics/dml.md) – Working with data
  - `INSERT`, `UPDATE`, `DELETE`
- [**DQL (Data Query Language)**](sql-basics/dql.md) – Fetching data
  - `SELECT`
---

## 3. **Important Concepts**
- [**Constraints**](important-concepts/constraints.md) - specify rules for the data in a table.
  - `NOT NULL`, `UNIQUE`, `PRIMARY KEY`, `FOREIGN KEY`, `CHECK`, `DEFAULT`, `CREATE INDEX`
- Data Types (INT, VARCHAR, DATE, etc.)
- Indexes (for faster search)
- Views
- Stored Procedures and Functions
- Triggers

---

## 4. **Advanced SQL**
- **Joins** (INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL JOIN)
- **Subqueries** (nested queries)
- **Aggregate Functions** (`SUM()`, `COUNT()`, `AVG()`, `MAX()`, `MIN()`)
- **GROUP BY** and **HAVING**
- **ORDER BY** and **LIMIT**

---

## 5. **Database Design (Modeling)**
- How to design efficient databases
- Normalization (1NF, 2NF, 3NF)
- ER Diagrams (Entity-Relationship diagrams)

---

## 6. **Practice, Practice, Practice**
- Build small projects (Student Management System, Library System, etc.)
- Solve real-world SQL problems on platforms like:
  - LeetCode (SQL section)
  - HackerRank (SQL track)
  - SQLZoo

---

## 7. **Learn RDBMS Tools**
- Install and use **MySQL Workbench**, **pgAdmin** (for PostgreSQL)
- Learn how to:
  - Export/Import data
  - Backup/Restore database

---

## 8. **Basics of Optimization**
- Query Optimization (write better, faster SQL)
- Understand Execution Plans
- Importance of Indexing

---

## 🎯 Bonus (if you want to go even deeper later)
- Transactions and ACID properties
- Concurrency Control (Locking, Deadlocks)
- Database Scaling (Sharding, Replication)