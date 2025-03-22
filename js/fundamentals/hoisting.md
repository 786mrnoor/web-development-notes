# Hoisting in JavaScript  

## What is Hoisting?  
**Hoisting** is JavaScript’s default behavior of **moving declarations to the top** of their scope **before execution**.  

> ✅ **Only declarations are hoisted, not initializations.**

---

## 1️⃣ Hoisting with `var`

🔹 **Variables declared with `var` are hoisted but not initialized.**  

```js
console.log(a); // Undefined (Hoisted but not initialized)
var a = 10;
console.log(a); // 10
```

**Internally, JavaScript treats it as:**

```js
var a;
console.log(a); // Undefined
a = 10;
console.log(a);
```

🔹 **If a `var` variable is used before declaration, it returns `undefined`, not an error.**

---

## 2️⃣ Hoisting with `let` and `const`
🔹 **`let` and `const` are hoisted but NOT initialized.**  

🔹 **They exist in the "Temporal Dead Zone (TDZ)" until their declaration is encountered.**

```js
console.log(b); // ❌ ReferenceError: Cannot access 'b' before initialization
let b = 20;

console.log(c); // ❌ ReferenceError
const c = 30;
```

✅ **Best Practice:** Always declare `let` and `const` before using them.

---

## 3️⃣ Hoisting with Functions

🔹 **Function declarations are fully hoisted** (both name & body).  

```js
greet(); // ✅ Works: "Hello"
function greet() {
  console.log("Hello");
}
```
🔹 **Function expressions (using `var`, `let`, or `const`) are NOT hoisted.**
```js
hello(); // ❌ TypeError: hello is not a function
var hello = function() {
  console.log("Hi");
};
```

---

## 4️⃣ Summary
| Type          | Hoisted? | Initialized? | Can Use Before Declaration? |
|--------------|----------|--------------|-----------------------------|
| `var`        | ✅ Yes   | ❌ No (gets `undefined`) | ✅ Yes (but `undefined`) |
| `let` / `const` | ✅ Yes   | ❌ No (TDZ Error) | ❌ No (ReferenceError) |
| Function Declaration | ✅ Yes | ✅ Yes | ✅ Yes |
| Function Expression | ✅ Yes | ❌ No | ❌ No (TypeError) |

---

### **Key Takeaways for Interviews**
✔ **`var` is hoisted but initialized as `undefined`.**  
✔ **`let` & `const` are hoisted but in TDZ, causing a ReferenceError if accessed before declaration.**  
✔ **Function declarations are fully hoisted, but function expressions are not.**  