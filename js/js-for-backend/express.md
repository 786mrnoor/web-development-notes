# Express.js

**Express.js** is a **minimal and flexible Node.js framework** that helps us build APIs and web servers easily.

---

## 📦 1. Install Express

```bash
npm init -y            # Create package.json
npm install express    # Install Express
```

---

## 🖥️ 2. Creating First Express App

```js
// server.js
const express = require("express");
const app = express();
const PORT = 3000;

app.get("/", (req, res) => {
  res.send("Hello, Express!");
});

app.listen(PORT, () => {
  console.log(`Server running at http://localhost:${PORT}`);
});
```

## 🔧 3. Basic Routing

```js
app.get("/about", (req, res) => {
  res.send("About Page");
});

app.post("/contact", (req, res) => {
  res.send("Contact Form Submitted");
});
```

---

## 🛠️ 4. Middleware

- Middleware intercepts requests before it reaches the intended route handler.
- Middleware functions can **modify requests/responses** or handle things like logging, security, etc.

```js
app.use(express.json()); // Parse incoming JSON

app.use((req, res, next) => {
  console.log(`${req.method} ${req.url}`);
  next();
});
```

---

## 📄 5. Sending JSON Data

```js
app.get("/api/user", (req, res) => {
  res.json({ name: "Noor", age: 22 });
});
```

---

## 📥 6. Accessing POST Data

```js
app.post("/api/data", (req, res) => {
  const userData = req.body;
  res.send(`Hello ${userData.name}`);
});
```

✅ Requires `express.json()` middleware!

---

## 🗂️ 7. Serving Static Files

```js
app.use(express.static("public"));
```

Put your HTML/CSS/JS files in a `public/` folder.

---

## 📌 8. REST API Example

```js
app.get("/users", (req, res) => {
  res.json([{ id: 1, name: "Ali" }]);
});

app.post("/users", (req, res) => {
  // Add user to DB (mocked)
  res.send("User added");
});

app.put("/users/:id", (req, res) => {
  res.send(`Updated user with ID: ${req.params.id}`);
});

app.delete("/users/:id", (req, res) => {
  res.send(`Deleted user with ID: ${req.params.id}`);
});
```

---

## ✅ Summary

| Concept          | Description                    |
| ---------------- | ------------------------------ |
| `express()`      | Initializes our app            |
| `app.get()`      | Handle GET requests            |
| `app.post()`     | Handle POST requests           |
| `express.json()` | Middleware to parse JSON       |
| `res.send()`     | Send a response                |
| `res.json()`     | Send JSON response             |
| `app.use()`      | Add middleware or static files |

---
