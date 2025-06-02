# DML (Data Manipulation Language)

## 🔑 Common DML Commands

| Command  | What it does                     |
| -------- | -------------------------------- |
| [`INSERT`](#1️⃣-insert-into) | Adds new rows                    |
| [`UPDATE`](#2️⃣-update) | Modifies existing rows           |
| [`DELETE`](#3️⃣-delete) | Removes rows                     |
| [`SELECT`](#4️⃣-optional-but-useful-select) | Retrieves data (technically DQL) |

👉 DML is used **after** your tables are already created using DDL.

---

## 1️⃣ **INSERT INTO**

**Add new data to a table.**

```sql
INSERT INTO students (firstname, lastname, date_of_birth, email)
VALUES ('John', 'Doe', '2006-01-01', 'john@gmail.com');
```

**Insert Multiple Rows.**

```sql
INSERT INTO students (firstname, lastname, date_of_birth, email)
VALUES 
    ('Chris', 'Haynes', '2006-01-31', 'chris@gmail.com'),
    ('Lana', 'Powell', '2005-12-05', 'lana@gmail.com'),
    ('Bria', 'Mason', '1998-05-26', 'bria@gmail.com');
```

---

## 2️⃣ **UPDATE**

**Change existing data in a table.**

```sql
UPDATE students
SET date_of_birth = '1999-02-01', email = 'dummy@gmail.com'
WHERE student_id = 1;
```

---

## 3️⃣ **DELETE**

**Remove data from a table.**

```sql
DELETE FROM students
WHERE student_id = 1;
```

---

## 4️⃣ *(Optional but useful)* **SELECT**

**Get data from the table (part of DQL but often grouped with DML).**

```sql
SELECT * FROM Students;
```

👉 Shows all students in the table.

---

### ⚠️ Important Note:

* Always use a **WHERE clause** with `UPDATE` and `DELETE` to avoid changing **every row** by mistake!

```sql
-- Bad:
DELETE FROM Students;  -- deletes all students!

-- Good:
DELETE FROM Students WHERE StudentID = 1;
```

---