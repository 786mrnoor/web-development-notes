# 🧮 MongoDB Aggregation Pipelines (with Mongoose)

## ✅ What is Aggregation?

Aggregation in MongoDB is used to **process data records** and return **computed results**. It works like a pipeline: **documents enter**, go through **multiple stages**, and come out **transformed or grouped**.

> Think of it like `.map()`, `.filter()`, `.reduce()` but on MongoDB documents.

---

## 🔧 Syntax

```js
Model.aggregate([
  { stage1 },
  { stage2 },
  ...
]);
```

Each **stage** uses an **operator** like `$match`, `$group`, `$project`, `$sort`, etc.

---

## 🗂️ Common Aggregation Stages

| Stage      | Purpose                                   |
| ---------- | ----------------------------------------- |
| `$match`   | Filter documents (like `find`)            |
| `$group`   | Group by a field and perform aggregation  |
| `$project` | Reshape documents (select, rename fields) |
| `$sort`    | Sort documents                            |
| `$limit`   | Limit the number of results               |
| `$skip`    | Skip documents (useful for pagination)    |
| `$lookup`  | Join (populate) with another collection   |
| `$unwind`  | Deconstruct arrays into multiple docs     |

---

## 📘 Example 1: Group by Course & Count Students

```js
Student.aggregate([
  {
    $group: {
      _id: "$course",
      total: { $sum: 1 }
    }
  }
]);
```

Output:

```json
[
  { "_id": "Web Dev", "total": 10 },
  { "_id": "Data Science", "total": 5 }
]
```

---

## 📘 Example 2: Match + Project + Sort

```js
Student.aggregate([
  { $match: { gender: "Male" } },
  { $project: { name: 1, course: 1, _id: 0 } },
  { $sort: { name: 1 } }
]);
```

---

## 📘 Example 3: Lookup (Join with Populate)

Assume:

* `posts` collection has `author` (ObjectId of user)
* `users` collection contains user details

```js
Post.aggregate([
  {
    $lookup: {
      from: "users",          // collection to join
      localField: "author",   // field in Post
      foreignField: "_id",    // field in User
      as: "authorDetails"     // output array
    }
  },
  { $unwind: "$authorDetails" } // turn array into object
]);
```

---

## 🛠️ Use Aggregation in Mongoose

```js
const results = await Student.aggregate([
  { $match: { course: "Web Dev" } },
  { $group: { _id: "$gender", count: { $sum: 1 } } }
]);
```

---

## 🧠 When to Use Aggregation?

* Reporting (counts, averages, totals)
* Data transformation (renaming, reshaping)
* Joins (`$lookup`)
* Analytics dashboards
* Advanced filtering

---

Would you like a **real project aggregation use case**, like:
“Show top 5 most active users with their total posts”?
