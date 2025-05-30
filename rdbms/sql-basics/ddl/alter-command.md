# ALTER COMMAND

The `ALTER` command adds, deletes, or modifies columns in a table.

- [`CHANGE`](): Can change a column name or definition, or both.
- [`MODIFY`](): Can change a column definition but not its name
- [`RENAME COLUMN`](): Can change a column name but not its definition

> Note: `CHANGE` and `MODIFY` can be followed by an optional `COLUMN` keyword.

## 1️⃣ Add a column(`ADD`)

```sql
ALTER TABLE Students
ADD Email VARCHAR(100);
```

👉 It adds a new column called `Email` to the `Students` table.

## 2️⃣ Delete a column(`DROP COLUMN`)

```sql
ALTER TABLE Customers
DROP COLUMN Email;
```

## 3️⃣ Modify an existing column(`MODIFY COLUMN` or `ALTER COLUMN`)

```sql
ALTER TABLE Student
MODIFY COLUMN Marks VARCHAR(3);
```
👉 It changes the data type of the column named `Marks` in the `Student` table to type `VARCHAR(3)`:

```sql
ALTER TABLE Employees
ALTER COLUMN BirthDate DATE; 
```
👉 It changes the data type of the column named `BirthDate` in the `Employees` table to type `DATE`:

## 4️⃣ RENAME a column(`RENAME COLUMN`)

```sql
ALTER TABLE Students
RENAME COLUMN RollNo TO EnrollementNo;
```

## 5️⃣ RENAME a table name(`RENAME TO`)

```sql
ALTER TABLE table_name
RENAME TO new_table_name;
```