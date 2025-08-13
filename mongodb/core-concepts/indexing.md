## 📚 1. **What Is an Index?**

- An **index** is a special data structure that stores a **small portion of the collection’s data** in an easily searchable form.
- **indexes** make data retrieval **faster and more efficient**. Without indexes, MongoDB has to **scan every document** (called a **collection scan**) which is slow for large collections.

---

## 🔍 2. **Default Index**

- Every document has an `_id` field.
- MongoDB **automatically creates an index on `_id`**.

```js
db.students.find({ _id: ObjectId("...") }); // fast
```

---

## 🚀 3. **Creating Indexes**

### ➤ Single Field Index

```js
db.students.createIndex({ name: 1 }); // ascending
db.students.createIndex({ age: -1 }); // descending
```

### ➤ Compound Index (multiple fields)

```js
db.students.createIndex({ course: 1, age: -1 });
```

### ➤ Unique Index

```js
db.students.createIndex({ email: 1 }, { unique: true });
```

---

## 📈 4. **View Indexes**

```js
db.students.getIndexes();
```

---

## ❌ 5. **Drop Index**

```js
db.students.dropIndex("name_1");
```

---

## 🛠 6. **Use explain() to Analyze Queries**

Check how MongoDB is executing your query — whether it uses an index or not:

```js
db.students.find({ name: "Noor" }).explain("executionStats");
```

Look for:

- `"stage": "IXSCAN"` = using index
- `"stage": "COLLSCAN"` = full scan (bad for large data)

---

## 🧠 7. When to Use Indexes?

| Use Case                  | Recommended Index Type       |
| ------------------------- | ---------------------------- |
| Search by name            | `{ name: 1 }`                |
| Sort by date              | `{ createdAt: -1 }`          |
| Search by multiple fields | `{ course: 1, age: -1 }`     |
| Prevent duplicate emails  | `{ email: 1 }, unique: true` |
| Query nested fields       | `{ "address.city": 1 }`      |

---

## ⚠️ 8. Things to Keep in Mind

- Indexes **consume RAM**
- Too many indexes = **slow write performance**
- Index only if the field is **frequently searched or sorted**

---
