# 🧠 MongoDB Data Types

MongoDB supports a wide range of **data types** to store structured, semi-structured, and unstructured data efficiently.

Here’s a breakdown of the most commonly used types:

---

## 🔢 1. **String** (`"string"`)

* Used to store text.

```js
{ name: "Noor Mohammad" }
```

---

## 🔢 2. **Number**

MongoDB distinguishes between several numeric types:

| Type         | Description                    |
| ------------ | ------------------------------ |
| `int`        | 32-bit integer                 |
| `long`       | 64-bit integer                 |
| `double`     | 64-bit floating point          |
| `decimal128` | High-precision decimal (money) |

```js
{ age: 23, salary: NumberDecimal("12345.67") }
```

---

## 🟢 3. **Boolean** (`true` / `false`)

```js
{ isStudent: true }
```

---

## 📅 4. **Date**

* Stores dates and times in ISODate format.

```js
{ joinedAt: new Date() }
```

> Internally stored as a 64-bit integer (milliseconds since epoch).

---

## 📜 5. **Array**

* Stores a list of values (can be mixed types).

```js
{ skills: ["HTML", "CSS", "JavaScript"] }
```

---

## 📄 6. **Object / Embedded Document**

* Stores another document inside a document.

```js
{
  address: {
    city: "Kolkata",
    zip: "700001"
  }
}
```

---

## 🆔 7. **ObjectId**

* A special 12-byte unique identifier automatically created for `_id`.

```js
{ _id: ObjectId("60a6f9e46d1b8e001f56e1ef") }
```

---

## 🧾 8. **Null**

* Represents an intentional empty value.

```js
{ middleName: null }
```

---

## 📎 9. **Binary Data**

* For storing files, images, etc. (often used with GridFS)

```js
{ fileData: BinData(0, "base64EncodedData") }
```

---

## 🧮 10. **Code**

* You can store JavaScript functions (rare use).

```js
{ compute: function() { return x + y; } }
```

---

## 🧩 11. **Regular Expression**

* For pattern matching in queries.

```js
{ name: /noor/i } // case-insensitive match
```

---

### 🧪 Full Document Example

```js
{
  _id: ObjectId("66225a6b1f1f6d001f1e7a10"),
  name: "Noor Mohammad",
  age: 23,
  isStudent: true,
  skills: ["HTML", "CSS", "JS"],
  address: {
    city: "Kolkata",
    pincode: "700001"
  },
  createdAt: new Date(),
  salary: NumberDecimal("15000.75"),
  isActive: null
}
```