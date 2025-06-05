# 🔗 What Are Joins in SQL?

**Joins** are used to **combine rows from two or more tables** based on a related column — usually a **primary key and foreign key**.

---

### 👨‍🎓 Example Tables We'll Use:

#### `Students`

| StudentID | Name  | CourseID |
| --------- | ----- | -------- |
| 1         | Alice | 101      |
| 2         | Bob   | 102      |
| 3         | Carol | 103      |

#### `Courses`

| CourseID | CourseName   |
| -------- | ------------ |
| 101      | Web Dev      |
| 102      | Data Science |
| 104      | UI/UX        |

---

## 🔸 1. `INNER JOIN` – Matching rows in both tables

✅ Returns **only matching rows** from both tables.

```sql
SELECT Students.Name, Courses.CourseName
FROM Students
INNER JOIN Courses ON Students.CourseID = Courses.CourseID;
```

🧾 Output:

| Name  | CourseName   |
| ----- | ------------ |
| Alice | Web Dev      |
| Bob   | Data Science |

---

## 🔸 2. `LEFT JOIN` (LEFT OUTER JOIN)

✅ Returns **all rows from the left table**, and matching rows from the right.
❌ If no match, right side is `NULL`.

```sql
SELECT Students.Name, Courses.CourseName
FROM Students
LEFT JOIN Courses ON Students.CourseID = Courses.CourseID;
```

🧾 Output:

| Name  | CourseName   |
| ----- | ------------ |
| Alice | Web Dev      |
| Bob   | Data Science |
| Carol | NULL         |

---

## 🔸 3. `RIGHT JOIN` (RIGHT OUTER JOIN)

✅ Returns **all rows from the right table**, and matching from the left.
❌ If no match, left side is `NULL`.

```sql
SELECT Students.Name, Courses.CourseName
FROM Students
RIGHT JOIN Courses ON Students.CourseID = Courses.CourseID;
```

🧾 Output:

| Name  | CourseName   |
| ----- | ------------ |
| Alice | Web Dev      |
| Bob   | Data Science |
| NULL  | UI/UX        |

---

## 🔸 4. `FULL OUTER JOIN`

✅ Returns **all rows from both tables**.
❌ If no match, fills with `NULL`.

> ⚠️ Not supported by MySQL directly, but you can simulate it with `UNION`.

```sql
SELECT Students.Name, Courses.CourseName
FROM Students
FULL OUTER JOIN Courses ON Students.CourseID = Courses.CourseID;
```

🧾 Output:

| Name  | CourseName   |
| ----- | ------------ |
| Alice | Web Dev      |
| Bob   | Data Science |
| Carol | NULL         |
| NULL  | UI/UX        |

---

## 🔸 5. `SELF JOIN`

✅ Joins a table **with itself** — useful for hierarchical or relational data like managers.

```sql
SELECT A.Name AS Employee, B.Name AS Manager
FROM Employees A
JOIN Employees B ON A.ManagerID = B.EmployeeID;
```

---

## 🔸 6. `CROSS JOIN` (Cartesian Product)

✅ Combines **every row** from the first table with **every row** from the second table.
⚠️ Grows fast with more rows — use carefully!

```sql
SELECT A.Name, B.CourseName
FROM Students A
CROSS JOIN Courses B;
```

🧾 If 3 students and 3 courses → 3 × 3 = **9 rows**.

---

## 🧠 Summary Table

| Join Type         | Description                               |
| ----------------- | ----------------------------------------- |
| `INNER JOIN`      | Only matching rows                        |
| `LEFT JOIN`       | All left rows + matched right rows        |
| `RIGHT JOIN`      | All right rows + matched left rows        |
| `FULL OUTER JOIN` | All rows from both sides                  |
| `SELF JOIN`       | Join a table with itself                  |
| `CROSS JOIN`      | Every combination of rows from both sides |
