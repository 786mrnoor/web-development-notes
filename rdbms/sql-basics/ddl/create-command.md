# CREATE COMMAND

## 1️⃣ **CREATE DATABASE**
```sql
CREATE DATABASE testDB;
```

👉 It creates a new database. we can check it in the list of databases with the `SHOW DATABASES;` SQL command.

## 2️⃣ **CREATE TABLE**

```sql
CREATE TABLE students (
    student_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    age INT,
    class VARCHAR(50)
);
```

👉 It Creates a `students` table with 4 columns.

---

## 3️⃣ Create Table Using Another Table

```sql
CREATE TABLE test_table AS
    SELECT name, age
    FROM students;
```
👉 It Creates a `test_table` table with 2 columns from `students` table.

## 4️⃣ CREATE INDEX
```sql
CREATE INDEX idx_name
ON students (name);
```
👉 It creates an index named `idx_name` on the `name` column in the `students` table:

```sql
CREATE INDEX idx_name_age
ON students (name, age);
```

## 5️⃣ CREATE UNIQUE INDEX
```sql
CREATE UNIQUE INDEX uidx_student
ON students (name, age, class);
```
👉 It creates an index named `uidx_student` on the `name`, `age`,  `class`, column in the `students` table: