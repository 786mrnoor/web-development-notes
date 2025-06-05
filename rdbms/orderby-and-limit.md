Great! Let's go through **`ORDER BY`** and **`LIMIT`** — two simple but super useful SQL clauses to **sort** and **control the number of results**. 📊🔽

---

## 🔸 `ORDER BY` – Sort Results

Used to **sort the result set** by one or more columns.

### ✅ Syntax:

```sql
SELECT column1, column2
FROM table_name
ORDER BY column1 [ASC|DESC];
```

* `ASC` = ascending (default)
* `DESC` = descending

---

### 📘 Example Table: `Students`

| StudentID | Name  | Marks |
| --------- | ----- | ----- |
| 1         | Alice | 85    |
| 2         | Bob   | 78    |
| 3         | Carol | 92    |
| 4         | David | 68    |
| 5         | Eva   | 90    |

---

### 🧪 Example 1: Order by Marks (Highest First)

```sql
SELECT Name, Marks
FROM Students
ORDER BY Marks DESC;
```

🧾 Output:

| Name  | Marks |
| ----- | ----- |
| Carol | 92    |
| Eva   | 90    |
| Alice | 85    |
| Bob   | 78    |
| David | 68    |

---

### 🧪 Example 2: Order by Name (A to Z)

```sql
SELECT Name, Marks
FROM Students
ORDER BY Name ASC;
```

---

## 🔸 `LIMIT` – Restrict Number of Rows

Used to **limit the number of rows** returned by the query.

### ✅ Syntax:

```sql
SELECT column1
FROM table_name
LIMIT number;
```

---

### 🧪 Example 3: Top 3 Students by Marks

```sql
SELECT Name, Marks
FROM Students
ORDER BY Marks DESC
LIMIT 3;
```

🧾 Output:

| Name  | Marks |
| ----- | ----- |
| Carol | 92    |
| Eva   | 90    |
| Alice | 85    |

---

### 🧪 Example 4: Skip Rows using `OFFSET`

```sql
SELECT Name, Marks
FROM Students
ORDER BY Marks DESC
LIMIT 2 OFFSET 2;
```

🧾 Output:

| Name  | Marks |
| ----- | ----- |
| Alice | 85    |
| Bob   | 78    |

> This skips the top 2 and returns the next 2.

---

## 🧠 Summary

| Clause     | Use Case                         |
| ---------- | -------------------------------- |
| `ORDER BY` | Sort rows by a column            |
| `LIMIT`    | Restrict number of returned rows |
| `OFFSET`   | Skip rows before limiting        |

---

### ✅ Combined Example

```sql
SELECT Name, Marks
FROM Students
WHERE Marks > 70
ORDER BY Marks DESC
LIMIT 5;
```