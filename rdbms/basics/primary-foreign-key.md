# 🔑 Primary Key

- **Primary Key** is a column (or group of columns) that **uniquely identifies** each row in a table.
- **No two rows** can have the same primary key value.
- It **cannot be NULL** — every row must have a value for it.

✅ It makes sure each record is **unique** and **findable** easily.

---

**Example:**

| StudentID (Primary Key) | Name  | Age |
|--------------------------|-------|-----|
| 1                        | John  | 20  |
| 2                        | Alice | 21  |
| 3                        | Bob   | 19  |

- Here, `StudentID` is the **Primary Key**.
- No two students can have the same `StudentID`.

---

# 🔗 Foreign Key

- **Foreign Key** is a column in one table that **links** to the **Primary Key** in another table.
- It creates a **relationship** between two tables.
- Helps **connect related data** across tables.

✅ It enforces **data integrity** — only valid links are allowed.

---

**Example:**

**Students Table:**

| StudentID (Primary Key) | Name  |
|--------------------------|-------|
| 1                        | John  |
| 2                        | Alice |

**Enrollments Table:**

| EnrollmentID | StudentID (Foreign Key) | CourseName |
|--------------|-------------------------|------------|
| 101          | 1                       | Math       |
| 102          | 2                       | Science    |

- In `Enrollments`, `StudentID` is a **Foreign Key** that points to `Students.StudentID`.
- It means Enrollment 101 belongs to John, and 102 belongs to Alice.

---

# 🧠 Quick Memory Tip:
| Key Type    | Meaning                          |
|-------------|-----------------------------------|
| Primary Key | Uniquely identifies inside a table |
| Foreign Key | Links one table to another table  |
