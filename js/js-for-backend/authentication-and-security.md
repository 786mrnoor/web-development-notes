Here's a clear and interview-friendly explanation of **Authentication & Security** concepts in web development, including **JWT**, **OAuth**, **CSRF**, and **CORS**:

---

## 🔐 Authentication vs Authorization

| Concept            | Description                                        |
| ------------------ | -------------------------------------------------- |
| **Authentication** | Verifying **who** a user is (login)                |
| **Authorization**  | Verifying **what** a user can access (permissions) |

---

## 1. 🪙 JSON Web Tokens (JWT)

### What is it?

JWT is a compact, URL-safe token used to securely **transmit information between client and server** after authentication.

### Structure:

```
header.payload.signature
```

### Use Case:

* After login, server sends JWT → client stores it (in localStorage or cookie)
* Client sends JWT in `Authorization` header for protected routes

### Why it's useful:

✅ Stateless
✅ Easily decoded (but not modifiable without secret)
✅ Works well with APIs

---

## 2. 🔐 OAuth (Open Authorization)

### What is it?

OAuth is a protocol that allows third-party apps to access user data **without sharing the password**.

### Example:

* You click “Login with Google”
* Google asks for your permission
* If you accept, it sends your info back to the app

### Use Case:

Used for **third-party logins** (Google, GitHub, Facebook, etc.)

### Flow:

1. Client app → Authorization server (Google)
2. User logs in → Gives permission
3. Server sends **access token**
4. Client uses access token to access user data

---

## 3. 🛡️ CSRF (Cross-Site Request Forgery)

### What is it?

A type of attack where a user is tricked into submitting an unwanted request (e.g., transferring money) **without their knowledge**.

### Example:

You're logged into your bank. A malicious site submits a form to `bank.com/transfer` using your cookies.

### Prevention:

* Use **CSRF tokens** in forms (server validates that the request came from the same app)
* Use **SameSite cookies**
* Avoid sensitive operations via GET

---

## 4. 🌐 CORS (Cross-Origin Resource Sharing)

### What is it?

A **browser security feature** that restricts one website from making requests to another domain.

### Example:

* You host frontend on `example.com`
* Your API is on `api.com`
* Browser blocks this unless `api.com` allows it

### How to fix:

* On the server (e.g., Express), set headers:

```js
res.setHeader("Access-Control-Allow-Origin", "http://example.com");
```

Or use middleware:

```js
const cors = require('cors');
app.use(cors({
  origin: 'http://example.com',
  credentials: true,
}));
```

---

## ✅ Summary Table

| Term  | Use Case                     | Protection/Usage                           |
| ----- | ---------------------------- | ------------------------------------------ |
| JWT   | Token-based authentication   | Store securely; use in API requests        |
| OAuth | Third-party login access     | Uses tokens (access/refresh)               |
| CSRF  | Prevent unauthorized actions | CSRF tokens, SameSite cookies              |
| CORS  | Secure cross-origin requests | Configure server to allow specific origins |

