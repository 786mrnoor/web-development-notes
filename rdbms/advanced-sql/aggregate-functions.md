# 📦 What Are Aggregate Functions?

Aggregate functions **operate on a set of values** (usually a column) and return a **single value** like total, average, max, etc.

They’re most commonly used with the `GROUP BY` clause.

---

## 🔑 Common Aggregate Functions

| Function  | Description                    |
| --------- | ------------------------------ |
| `SUM()`   | Adds all the values            |
| `COUNT()` | Counts rows or non-NULL values |
| `AVG()`   | Calculates the average (mean)  |
| `MAX()`   | Finds the highest value        |
| `MIN()`   | Finds the lowest value         |

---

## 📘 Example Table: `Students`

| StudentID | Name  | Marks | Course   |
| --------- | ----- | ----- | -------- |
| 1         | Alice | 85    | Web Dev  |
| 2         | Bob   | 78    | Web Dev  |
| 3         | Carol | 92    | Data Sci |
| 4         | David | 68    | Data Sci |
| 5         | Eva   | 90    | Web Dev  |

---

## 🔢 1. `SUM()` – Total of a column

```sql
SELECT SUM(Marks) AS TotalMarks FROM Students;
```

**🧾 Output:** `413`

---

## 🔢 2. `COUNT()` – Count of rows

```sql
SELECT COUNT(*) AS TotalStudents FROM Students;
```

**🧾 Output:** `5`

You can also count specific columns:

```sql
SELECT COUNT(Marks) AS MarksCount FROM Students;
```

This ignores `NULL` values in `Marks`.

---

## 🔢 3. `AVG()` – Average value

```sql
SELECT AVG(Marks) AS AvgMarks FROM Students;
```

**🧾 Output:** `82.6`

---

## 🔢 4. `MAX()` and `MIN()`

```sql
SELECT MAX(Marks) AS Highest, MIN(Marks) AS Lowest FROM Students;
```

**🧾 Output:** `Highest: 92`, `Lowest: 68`

---

## 🔀 Grouping Data: `GROUP BY`

Get **average marks per course**:

```sql
SELECT Course, AVG(Marks) AS AvgMarks
FROM Students
GROUP BY Course;
```

**🧾 Output:**

| Course   | AvgMarks |
| -------- | -------- |
| Web Dev  | 84.33    |
| Data Sci | 80.00    |

---

## ⚠️ Notes

* Aggregate functions **ignore NULLs** (except `COUNT(*)`)
* You can **combine with `HAVING`** to filter groups:

  ```sql
  SELECT Course, AVG(Marks)
  FROM Students
  GROUP BY Course
  HAVING AVG(Marks) > 80;
  ```

---

## 🧠 Summary

| Function  | Example                     | Description     |
| --------- | --------------------------- | --------------- |
| `SUM()`   | `SUM(Marks)`                | Total of column |
| `COUNT()` | `COUNT(*)` or `COUNT(Name)` | Row count       |
| `AVG()`   | `AVG(Marks)`                | Mean (average)  |
| `MAX()`   | `MAX(Marks)`                | Highest value   |
| `MIN()`   | `MIN(Marks)`                | Lowest value    |
