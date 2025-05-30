# 🛠️ DDL

**DDL (Data Definition Language)** is a part of SQL that helps you:

👉 It's about **defining** the **blueprint** of your database — not the data itself.

## 🔧 Common DDL Commands:

| Command    | What it does                     |
| ---------- | -------------------------------- |
| [`CREATE`](ddl/create-command.md)   | Creates a new table or database  |
| [`ALTER`](ddl/alter-command.md)    | adds, deletes, or modifies columns in a table. |
| `DROP`     | Deletes a table or database      |
| `TRUNCATE` | Deletes all data but keeps table |
| `RENAME`   | Changes the name of a table      |


### 3. **DROP TABLE**

```sql
DROP TABLE Students;
```

👉 Deletes the entire `Students` table and all its data ⚠️ (use carefully).

---

### 4. **TRUNCATE TABLE**

```sql
TRUNCATE TABLE Students;
```

👉 Deletes **all rows** in the table, but **keeps the structure**.

---

### 5. **RENAME TABLE**

```sql
RENAME TABLE Students TO Learners;
```

👉 Renames the table from `Students` to `Learners`.
