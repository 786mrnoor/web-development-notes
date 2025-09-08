# MongoDB Update Operators

MongoDB provides special **update operators** to modify documents without replacing the whole document.

## 🔑 Common Update Operators

| Operator           | Use Case                       | Example                                   |
| ------------------ | ------------------------------ | ----------------------------------------- |
| **`$set`**         | Set or update a field’s value  | `{ $set: { age: 25 } }`                   |
| **`$unset`**       | Remove a field                 | `{ $unset: { age: "" } }`                 |
| **`$inc`**         | Increment/decrement a value    | `{ $inc: { score: 5 } }`                  |
| **`$mul`**         | Multiply a field’s value       | `{ $mul: { price: 1.1 } }`                |
| **`$rename`**      | Rename a field                 | `{ $rename: { oldName: "newName" } }`     |
| **`$min`**         | Update if new value is smaller | `{ $min: { price: 50 } }`                 |
| **`$max`**         | Update if new value is larger  | `{ $max: { price: 100 } }`                |
| **`$currentDate`** | Set field to current date/time | `{ $currentDate: { lastUpdated: true } }` |

---

## 🔑 Array Update Operators

| Operator        | Use Case                                  | Example                                               |
| --------------- | ----------------------------------------- | ----------------------------------------------------- |
| **`$push`**     | Add element to array                      | `{ $push: { tags: "new" } }`                          |
| **`$addToSet`** | Add if not exists (like Set)              | `{ $addToSet: { tags: "unique" } }`                   |
| **`$pop`**      | Remove first (`-1`) or last (`1`) element | `{ $pop: { tags: 1 } }`                               |
| **`$pull`**     | Remove matching value                     | `{ $pull: { tags: "old" } }`                          |
| **`$pullAll`**  | Remove multiple values                    | `{ $pullAll: { tags: ["a","b"] } }`                   |
| **`$each`**     | Push multiple values                      | `{ $push: { tags: { $each: ["x","y"] } } }`           |
| **`$position`** | Insert at specific index                  | `{ $push: { tags: { $each: ["x"], $position: 1 } } }` |

---

### 📌 Example Usage

```js
db.users.updateOne(
  { name: "Noor" },
  {
    $set: { age: 30 },
    $inc: { logins: 1 },
    $push: { tags: "active" },
  }
);
```

---
