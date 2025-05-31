# ALTER COMMAND

The `ALTER` command adds, deletes, or modifies columns in a table.

## 1️⃣ Add a column(`ADD`)

```sql
ALTER TABLE students
ADD COLUMN email VARCHAR(100); -- COLUMN is optional
```

👉 It adds a new column called `email` to the `students` table.

## 2️⃣ Delete a column(`DROP COLUMN`)

```sql
ALTER TABLE students
DROP COLUMN email; -- COLUMN is optional
```

## 3️⃣ Modify an existing column(`MODIFY COLUMN`)

```sql
ALTER TABLE students
MODIFY COLUMN email VARCHAR(20); -- COLUMN is optional
```
👉 It changes the data type of the column named `email` in the `students` table to type `VARCHAR(20)`:


## 4️⃣ RENAME a column(`CHANGE COLUMN`)

```sql
ALTER TABLE students
CHANGE COLUMN email student_email VARCHAR(25); -- COLUMN is optional
```

## 5️⃣ RENAME a table name(`RENAME TO`)

```sql
ALTER TABLE students
RENAME TO new_students;
```

- [`CHANGE`](): Can change a column name and definition.
- [`MODIFY`](): Can change a column definition but not its name
