## 🔹 `GROUP BY` – Group rows based on one or more columns

It’s used **with aggregate functions** (`SUM()`, `COUNT()`, `AVG()`, etc.) to get results per group.

### 📘 Example Table: `Sales`

| SaleID | Product | Quantity | Amount |
| ------ | ------- | -------- | ------ |
| 1      | Apple   | 10       | 100    |
| 2      | Banana  | 5        | 50     |
| 3      | Apple   | 7        | 70     |
| 4      | Banana  | 6        | 60     |
| 5      | Orange  | 8        | 80     |

---

### ✅ Example: Total sales per product

```sql
SELECT Product, SUM(Amount) AS TotalSales
FROM Sales
GROUP BY Product;
```

🧾 Output:

| Product | TotalSales |
| ------- | ---------- |
| Apple   | 170        |
| Banana  | 110        |
| Orange  | 80         |

---

## 🔹 `HAVING` – Filter grouped results

`HAVING` is like `WHERE`, **but for groups**.

> You **cannot** use aggregate functions in `WHERE`, only in `HAVING`.

---

### ✅ Example: Only products with sales > 100

```sql
SELECT Product, SUM(Amount) AS TotalSales
FROM Sales
GROUP BY Product
HAVING SUM(Amount) > 100;
```

🧾 Output:

| Product | TotalSales |
| ------- | ---------- |
| Apple   | 170        |
| Banana  | 110        |

---

## 🔁 `GROUP BY` + `HAVING` + `ORDER BY`

```sql
SELECT Product, SUM(Quantity) AS TotalQty
FROM Sales
GROUP BY Product
HAVING SUM(Quantity) >= 10
ORDER BY TotalQty DESC;
```

---

## 🧠 Summary Table

| Clause     | Purpose                                  |
| ---------- | ---------------------------------------- |
| `GROUP BY` | Group rows by one or more columns        |
| `HAVING`   | Filter the grouped rows (with aggregate) |
| `WHERE`    | Filter rows **before** grouping          |

---

## ⚠️ Tips

* Use `GROUP BY` **before** `HAVING`
* You **can’t** use `WHERE` with `SUM()`, `AVG()` — use `HAVING` instead

---

## ✅ Real-Life Use Cases

* Students: Average marks per subject
* Orders: Total amount per customer
* Employees: Highest salary by department

