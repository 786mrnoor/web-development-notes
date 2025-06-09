# 🔗 Connecting to MongoDB with Mongoose in Node.js

Here’s a simple guide on how to connect your Node.js app to MongoDB using **Mongoose**.

---

## Step 1: Install Mongoose

Run in your project directory:

```bash
npm install mongoose
```

---

## Step 2: Import & Connect

```js
const mongoose = require('mongoose');

const uri = 'mongodb://localhost:27017/mydatabase'; // local MongoDB URL
// OR MongoDB Atlas cloud URL, e.g.
// const uri = 'mongodb+srv://username:password@cluster0.mongodb.net/mydatabase?retryWrites=true&w=majority';

mongoose.connect(uri, {
  useNewUrlParser: true,
  useUnifiedTopology: true,
})
.then(() => {
  console.log("Connected to MongoDB successfully!");
})
.catch((err) => {
  console.error("Error connecting to MongoDB:", err);
});
```

---

## Optional: Handling Connection Events

```js
mongoose.connection.on('connected', () => {
  console.log('Mongoose connected to DB');
});

mongoose.connection.on('error', (err) => {
  console.log('Mongoose connection error:', err);
});

mongoose.connection.on('disconnected', () => {
  console.log('Mongoose disconnected');
});
```
