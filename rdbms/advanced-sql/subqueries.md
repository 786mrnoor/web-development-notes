# 🔍 What is a Subquery?

A **subquery** is a query **inside another query**.

* It returns data used by the **main (outer) query**
* Can be placed in `SELECT`, `FROM`, or `WHERE` clauses

---

## 📦 Types of Subqueries

| Type           | Description                                   | Returns     |
| -------------- | --------------------------------------------- | ----------- |
| **Scalar**     | Returns a single value                        | One value   |
| **Row/Column** | Returns a single row or column                | One row/col |
| **Table**      | Returns a full result set                     | Many rows   |
| **Correlated** | Depends on the outer query, runs for each row | Varies      |

---

## ✅ 1. Subquery in `WHERE` clause

**Find students who scored more than the average score:**

```sql
SELECT Name
FROM Students
WHERE Marks > (SELECT AVG(Marks) FROM Students);
```

* The subquery runs first: `(SELECT AVG(Marks)...)`
* The outer query uses its result

---

## ✅ 2. Subquery in `SELECT` clause

**Add a column showing average marks for reference:**

```sql
SELECT Name, Marks,
  (SELECT AVG(Marks) FROM Students) AS AvgMarks
FROM Students;
```

---

## ✅ 3. Subquery in `FROM` clause (inline view)

**Get highest scorer from a temporary result set:**

```sql
SELECT Name, Marks
FROM (
  SELECT Name, Marks FROM Students
  ORDER BY Marks DESC LIMIT 1
) AS Topper;
```

---

## ✅ 4. `IN`, `ANY`, `ALL`, `EXISTS` with subqueries

### 📌 Use with `IN`

```sql
SELECT Name FROM Students
WHERE CourseID IN (SELECT CourseID FROM Courses WHERE CourseName = 'Web Dev');
```

### 📌 Use with `EXISTS`

```sql
SELECT Name
FROM Students s
WHERE EXISTS (
  SELECT 1 FROM Courses c WHERE c.CourseID = s.CourseID AND c.CourseName = 'Web Dev'
);
```

---

## 🔁 Correlated Subquery

A subquery that runs **once per outer row**.

```sql
SELECT Name, Marks
FROM Students s
WHERE Marks > (
  SELECT AVG(Marks)
  FROM Students
  WHERE CourseID = s.CourseID
);
```

* The subquery depends on each row of the outer query.

---

## 🧠 Summary

| Clause Used In | Purpose                                |
| -------------- | -------------------------------------- |
| `SELECT`       | Add dynamic columns                    |
| `FROM`         | Treat subquery as a temporary table    |
| `WHERE`        | Filter based on another query’s result |
| `IN`/`EXISTS`  | Conditional subquery checks            |

---

## ⚠️ Subquery Tips

* Always give **alias names** to subqueries in `FROM`
* Use subqueries for **modular**, readable logic
* Prefer **JOINs** if performance becomes an issue
