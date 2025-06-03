# 🧠 What is DQL?

**DQL (Data Query Language)** is a part of SQL used to **query (retrieve)** data from tables.

🟢 It **does not change** the data — it just **reads** it.

👉 The main (and only) DQL command is: **`SELECT`**

---

## 🔍 The `SELECT` Statement

The `SELECT` statement is used to **get specific data** from one or more tables.

---

### ✅ Basic Syntax:

```sql
SELECT column1, column2
FROM table_name;
```

Or to get **all columns**:

```sql
SELECT * FROM table_name;
```

---

## 📘 Examples

### 1. **Select all columns**

```sql
SELECT * FROM Students;
```

### 2. **Select specific columns**

```sql
SELECT Name, Age FROM Students;
```

---

## 🎯 Add Conditions (Filtering)

### 3. **Using WHERE clause**

```sql
SELECT * FROM Students
WHERE Age > 18;
```

### 4. **Using ORDER BY (sorting)**

```sql
SELECT * FROM Students
ORDER BY Age DESC;
```

---

## 📊 Aggregations + Grouping

### 5. **COUNT, SUM, AVG, MAX, MIN**

```sql
SELECT COUNT(*) FROM Students;
```

### 6. **GROUP BY**

```sql
SELECT Class, COUNT(*) 
FROM Students
GROUP BY Class;
```

---

## 🔄 Combine with other clauses:

| Clause     | Purpose                                 |
| ---------- | --------------------------------------- |
| `WHERE`    | Filter rows                             |
| `ORDER BY` | Sort results                            |
| `GROUP BY` | Group similar data                      |
| `HAVING`   | Filter groups (like WHERE for GROUP BY) |
| `LIMIT`    | Show limited number of rows             |

---

### 📌 Example Query with All:

```sql
SELECT Class, COUNT(*) AS Total
FROM Students
WHERE Age > 18
GROUP BY Class
HAVING COUNT(*) > 1
ORDER BY Total DESC
LIMIT 5;
```

---

### 🧠 Summary:

| DQL Command | Purpose       |
| ----------- | ------------- |
| `SELECT`    | Retrieve data |

---

Would you like a **set of small DQL exercises** for practice (like “Get all students over age 20”)?
It's a great way to get hands-on! 🧩💡
