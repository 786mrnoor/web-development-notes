# ⚡ What is an Index in SQL?

An **index** is a **data structure** that improves the speed of **read operations** like `SELECT`, especially on large tables.

✅ It allows the database to **quickly locate rows** based on column values
🚫 It does **not** affect the actual data or its structure.

---

## 🧠 Why Use Indexes?

| Without Index                 | With Index                               |
| ----------------------------- | ---------------------------------------- |
| Scans the entire table (slow) | Jumps directly to matching rows (fast)   |
| Slower searches and filters   | Faster queries, especially on large data |
| Saves no extra space          | Uses more memory to speed up queries     |

---

## 🛠️ Basic Syntax to Create Index

```sql
CREATE INDEX index_name
ON table_name (column1, column2, ...);
```

---

## ✅ Example:

```sql
CREATE INDEX idx_name
ON Students (Name);
```

* This index helps speed up queries like:

```sql
SELECT * FROM Students WHERE Name = 'John';
```

---

## 📛 Naming Tip:

By convention, index names often start with `idx_` followed by table/column names.

---

## 🔍 Types of Indexes

| Index Type        | Description                                                |
| ----------------- | ---------------------------------------------------------- |
| **Single-column** | Index on one column                                        |
| **Composite**     | Index on multiple columns (e.g., `(LastName, FirstName)`)  |
| **Unique Index**  | Ensures no duplicate values                                |
| **Primary Key**   | Automatically creates a unique index                       |
| **Full-text**     | For efficient searching within large text (MySQL-specific) |

---

## 🔄 Remove Index

```sql
DROP INDEX index_name ON table_name;
```

---

## ⚠️ Index Trade-offs

| ✅ Pros                                  | ❌ Cons                          |
| --------------------------------------- | ------------------------------- |
| Speeds up SELECT queries                | Slows down INSERT/UPDATE/DELETE |
| Helps with sorting and filtering        | Uses extra disk space           |
| Enforces uniqueness (with unique index) | Too many indexes = overhead     |

---

## 📘 Example Use Cases

* Search by name, email, phone
* Frequently filtered columns (`WHERE status = 'Active'`)
* Foreign keys (for fast joins)

---

## 🧠 Summary

| Concept  | Description                                         |
| -------- | --------------------------------------------------- |
| Index    | Speeds up lookups/search in a table                 |
| Syntax   | `CREATE INDEX index_name ON table (col);`           |
| Use when | Column is often used in `WHERE`, `JOIN`, `ORDER BY` |
| Cost     | More storage + slower inserts/updates               |
