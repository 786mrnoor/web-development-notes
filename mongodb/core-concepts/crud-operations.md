# 🔧 MongoDB CRUD Operations using Native Methods

MongoDB supports the standard **CRUD** operations — **Create, Read, Update, Delete** — using simple methods. Below is a clean overview with examples:

---

## 📥 1. **Create (Insert)**

### ➤ `insertOne()`

Inserts a **single document** into a collection.

```js
db.students.insertOne({
  name: "Noor",
  age: 23,
  course: "Web Development"
});
```

### ➤ `insertMany()`

Inserts **multiple documents** at once.

```js
db.students.insertMany([
  { name: "Ali", age: 22, course: "Data Science" },
  { name: "Sara", age: 24, course: "Cybersecurity" }
]);
```

---

## 🔍 2. **Read (Find)**

### ➤ `find()`

Returns **multiple documents** (as a cursor).

```js
db.students.find(); // All students

db.students.find({ course: "Web Development" }); // Filtered
```

### ➤ `findOne()`

Returns **first matching document**.

```js
db.students.findOne({ name: "Noor" });
```

---

## 🛠️ 3. **Update**

### ➤ `updateOne()`

Updates the **first matching document**.

```js
db.students.updateOne(
  { name: "Noor" },          // filter
  { $set: { age: 24 } }      // update
);
```

### ➤ `updateMany()`

Updates **all matching documents**.

```js
db.students.updateMany(
  { course: "Web Development" },
  { $set: { isActive: true } }
);
```

---

## 🗑️ 4. **Delete**

### ➤ `deleteOne()`

Deletes the **first matching document**.

```js
db.students.deleteOne({ name: "Ali" });
```

### ➤ `deleteMany()`

Deletes **all matching documents**.

```js
db.students.deleteMany({ course: "Cybersecurity" });
```

---

## 📘 Tip: Use `pretty()` to format results

```js
db.students.find().pretty();
```

---

## 🧪 Bonus: Filter Examples

| Use Case                  | Query Example                                   |
| ------------------------- | ----------------------------------------------- |
| Age greater than 20       | `{ age: { $gt: 20 } }`                          |
| Name starts with “S”      | `{ name: /^S/ }`                                |
| Match multiple conditions | `{ age: { $gte: 22 }, course: "Data Science" }` |

---