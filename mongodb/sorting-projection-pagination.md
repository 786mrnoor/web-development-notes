## 🔢 1. Sorting

Sorting lets you order the query results by one or more fields.

* **Syntax:**

```js
db.collection.find().sort({ field1: 1, field2: -1 });
```

* `1` means ascending order
* `-1` means descending order

**Example:** Sort students by age ascending and name descending

```js
db.students.find().sort({ age: 1, name: -1 });
```

---

## 👁️‍🗨️ 2. Projection

Projection lets you specify which fields to include or exclude in the query result.

* **Syntax:**

```js
db.collection.find({}, { field1: 1, field2: 1, _id: 0 });
```

* `1` to include field
* `0` to exclude field
* By default, `_id` is included, so you often exclude it explicitly if you want.

**Example:** Return only `name` and `course`, exclude `_id`

```js
db.students.find({}, { name: 1, course: 1, _id: 0 });
```

---

## 📄 3. Pagination

Pagination splits results into pages — very useful for large datasets.

* Use **`skip()`** and **`limit()`** methods.

**Syntax:**

```js
db.collection.find().skip(n).limit(m);
```

* `skip(n)` — skips the first `n` documents
* `limit(m)` — limits the result to `m` documents

**Example:** Get page 3 with 5 items per page

```js
const page = 3;
const limit = 5;
const skip = (page - 1) * limit;

db.students.find().skip(skip).limit(limit);
```

---

### 📦 Combined Example

Get the 2nd page of students enrolled in "Web Development," sorted by `age` descending, only showing `name` and `age`:

```js
const page = 2;
const limit = 5;
const skip = (page - 1) * limit;

db.students.find({ course: "Web Development" }, { name: 1, age: 1, _id: 0 })
  .sort({ age: -1 })
  .skip(skip)
  .limit(limit);
```

---