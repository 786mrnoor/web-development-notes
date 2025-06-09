# 📦 MongoDB: Database, Collection, and Document

MongoDB stores data in a **hierarchical structure**:

```
MongoDB ➝ Database ➝ Collection ➝ Document
```

Let’s break it down:

---

## 🗄️ 1. **Database**

* A **MongoDB database** is a container for collections.
* You can have **multiple databases** in a MongoDB server.
* Example: `schoolDB`, `ecommerceDB`, `blogDB`

#### 👉 Create a database (in Mongo shell):

```js
use schoolDB
```

---

## 📁 2. **Collection**

* A **collection** is like a **table** in SQL.
* It holds multiple **documents**.
* Collections are **schema-less** (documents can have different fields).

#### Examples:

* In `schoolDB`: `students`, `teachers`, `courses`
* In `ecommerceDB`: `products`, `orders`, `customers`

#### 👉 Create a collection:

```js
db.createCollection("students")
```

Or automatically created when inserting:

```js
db.students.insertOne({ name: "Noor", age: 23 })
```

---

## 📄 3. **Document**

* A **document** is a **single record** (like a row in SQL).
* It’s stored as **BSON** (Binary JSON).
* It contains **key-value pairs**.
* Each document has a unique `_id` field.

#### 👉 Example Document:

```json
{
  "_id": ObjectId("66225a6b1f1f6d001f1e7a10"),
  "name": "Noor Mohammad",
  "age": 23,
  "course": "Web Development"
}
```

#### 👉 Insert Document:

```js
db.students.insertOne({
  name: "Noor Mohammad",
  age: 23,
  course: "Web Development"
});
```

---

### 📌 Analogy with SQL:

| SQL Term | MongoDB Equivalent |
| -------- | ------------------ |
| Database | Database           |
| Table    | Collection         |
| Row      | Document           |
| Column   | Field (key)        |

---

### ⚡ Quick Example

```js
// Switch to a database
use ecommerceDB;

// Insert a document into a collection
db.products.insertOne({
  name: "Laptop",
  price: 45000,
  brand: "Dell"
});
```
