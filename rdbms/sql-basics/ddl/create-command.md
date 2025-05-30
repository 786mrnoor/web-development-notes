# CREATE COMMAND

## 1️⃣ **CREATE DATABASE**
```sql
CREATE DATABASE testDB;
```

👉 It creates a new database. we can check it in the list of databases with the `SHOW DATABASES;` SQL command.

## 2️⃣ **CREATE TABLE**

```sql
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(100),
    Age INT,
    Class VARCHAR(50)
);
```

👉 It Creates a `Students` table with 4 columns.

---

## 3️⃣ Create Table Using Another Table

```sql
CREATE TABLE TestTable AS
    SELECT customername, contactname
    FROM customers;
```
👉 It Creates a `TestTable` table with 2 columns from `customers` table.

## 4️⃣ CREATE INDEX
```sql
CREATE INDEX idx_lastname
ON Persons (LastName);
```
👉 It creates an index named `idx_lastname` on the `LastName` column in the `Persons` table:

```sql
CREATE INDEX idx_pname
ON Persons (LastName, FirstName);
```

## 5️⃣ CREATE UNIQUE INDEX
```sql
CREATE UNIQUE INDEX uidx_pid
ON Persons (PersonID);
```
👉 It creates an index named `uidx_pid` on the `PersonID` column in the `Persons` table: