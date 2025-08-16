# 🔍 MongoDB Filtering & Query Operators Cheat Sheet

MongoDB provides **powerful query operators** to filter documents. These operators allow **comparison, logical conditions, array matching**, and more.

---

## ✅ 1. **Comparison Operators**

| Operator | Description                | Example                                   |
| -------- | -------------------------- | ----------------------------------------- |
| `$eq`    | Equal to                   | `{ age: { $eq: 25 } }`                    |
| `$ne`    | Not equal to               | `{ name: { $ne: "Ali" } }`                |
| `$gt`    | Greater than               | `{ age: { $gt: 18 } }`                    |
| `$gte`   | Greater than or equal      | `{ age: { $gte: 21 } }`                   |
| `$lt`    | Less than                  | `{ age: { $lt: 30 } }`                    |
| `$lte`   | Less than or equal         | `{ age: { $lte: 25 } }`                   |
| `$in`    | Matches any value in array | `{ course: { $in: ["DS", "AI"] } }`       |
| `$nin`   | Not in the array           | `{ course: { $nin: ["Python", "C++"] } }` |

---

## 🔁 2. **Logical Operators**

| Operator | Description                     | Example                                                   |
| -------- | ------------------------------- | --------------------------------------------------------- |
| `$and`   | All conditions must be true     | `{ $and: [ { age: { $gt: 18 } }, { isStudent: true } ] }` |
| `$or`    | At least one condition is true  | `{ $or: [ { age: { $lt: 18 } }, { course: "Java" } ] }`   |
| `$not`   | Negates a condition             | `{ age: { $not: { $gt: 30 } } }`                          |
| `$nor`   | None of the conditions are true | `{ $nor: [ { age: { $gt: 30 } }, { isStudent: true } ] }` |

---

## 📑 3. **Element Operators**

| Operator  | Description                | Example                             |
| --------- | -------------------------- | ----------------------------------- |
| `$exists` | Checks if the field exists | `{ middleName: { $exists: true } }` |
| `$type`   | Checks the BSON type       | `{ age: { $type: "int" } }`         |

---

## 🔄 4. **Array Operators**

| Operator     | Description                                      | Example                                             |
| ------------ | ------------------------------------------------ | --------------------------------------------------- |
| `$all`       | Matches all elements in array                    | `{ skills: { $all: ["HTML", "CSS"] } }`             |
| `$size`      | Matches array with given size                    | `{ skills: { $size: 3 } }`                          |
| `$elemMatch` | Matches documents in array that match conditions | `{ scores: { $elemMatch: { $gt: 90, $lt: 100 } } }` |

---

## 🔍 5. **Regex (Pattern Matching)**

```js
{ name: /noor/i } // case-insensitive match
{ email: { $regex: "^admin", $options: "i" } } // starts with 'admin'
```

---

## 🔧 Combined Example

```js
db.students.find({
  $and: [
    { age: { $gte: 20, $lte: 25 } },
    { course: { $in: ["Web Dev", "DS"] } },
    { isStudent: true },
  ],
});
```

---

### 📌 Notes

- You can use **dot notation** to query nested fields:
  `{ "address.city": "Delhi" }`
- Combine operators for more complex filters.

---
