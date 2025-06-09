# 📚 Mongoose Schemas and Models

---

## 1. **Schema**

* Defines the **structure** of documents in a MongoDB collection.
* Specifies **fields**, their **types**, **validation**, **default values**, etc.
* Acts like a blueprint for the data.

---

### Example Schema

```js
const mongoose = require('mongoose');

const userSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true,           // Validation: must be provided
    trim: true                // Remove whitespace
  },
  email: {
    type: String,
    required: true,
    unique: true,             // Unique index
    lowercase: true
  },
  age: {
    type: Number,
    min: 0,
    max: 120,
    default: 18
  },
  createdAt: {
    type: Date,
    default: Date.now
  }
});
```

---

## 2. **Model**

* A **Model** is a class compiled from the Schema.
* Represents a MongoDB **collection**.
* Provides an interface to **create**, **query**, **update**, and **delete** documents.

---

### Creating a Model

```js
const User = mongoose.model('User', userSchema);
```

* Here, `'User'` is the model name.
* Mongoose will create (or use) a collection named `'users'` (plural, lowercase) in MongoDB.

---

## 3. **Using Schema and Model**

### Creating a new user document:

```js
const newUser = new User({
  name: "Noor Mohammad",
  email: "noor@example.com",
  age: 25
});

newUser.save()
  .then(doc => console.log("User saved:", doc))
  .catch(err => console.error(err));
```

### Querying users:

```js
User.find({ age: { $gte: 18 } })
  .then(users => console.log(users))
  .catch(err => console.error(err));
```

---

## Summary:

| Concept    | Description                              |
| ---------- | ---------------------------------------- |
| **Schema** | Defines the structure & validation rules |
| **Model**  | Provides interface to MongoDB collection |
