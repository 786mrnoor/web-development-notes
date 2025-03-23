# Scope & Closures in JavaScript 

## 1️⃣ Scope in JavaScript

Scope determines **where a variable is accessible** in the code.

### **1.1 Global Scope**

Variables declared outside any function or block create global scope and accessible anywhere in the code.  

```js
let globalVar = "I'm global"; 

function test() {
  console.log(globalVar); // ✅ Accessible
}
test();
console.log(globalVar); // ✅ Accessible
```

### **1.2 Function Scope**

- Variables declared inside a function are **only accessible within that function**.  
- Uses `var`, `let`, or `const`.  

```js
function example() {
  let localVar = "I'm local";
  console.log(localVar); // ✅ Accessible inside function
}
example();
console.log(localVar); // ❌ ReferenceError (Not accessible outside)
```

### **1.3 Block Scope** (`let` & `const`)

- Variables declared inside `{}` using `let` or `const` **cannot be accessed outside**.  

```js
{
  let blockVar = "I'm inside a block";
  console.log(blockVar); // ✅ Accessible
}
console.log(blockVar); // ❌ ReferenceError
```

### **1.4 Lexical Scope**  

- **Inner functions** have access to variables from their outer functions (parent scope).  

```js
function outer() {
  let outerVar = "I’m outer";
  
  function inner() {
    console.log(outerVar); // ✅ Accessible (Lexical Scope)
  }
  inner();
}
outer();
```
---

# 2️⃣ Closures in JavaScript

A **closure** is a function that **remembers variables from its outer scope even after the outer function has finished executing**.

## 2.1 Example of Closure

```js
function outerFunction() {
  let count = 0; // Private variable
  
  return function innerFunction() {
    count++;
    console.log(count);
  };
}

const counter = outerFunction();
counter(); // 1
counter(); // 2
counter(); // 3
```
🔹 **How it works?**  

- `innerFunction` **remembers** `count`, even after `outerFunction` has returned.  
- This creates a **private state** that only `innerFunction` can modify.  

## 2.2 Closures in Real-World Use Cases

✅ **Data privacy & Encapsulation**  

```js
function bankAccount(initialBalance) {
  let balance = initialBalance;
  
  return {
    deposit(amount) {
      balance += amount;
      console.log(`Deposited: ${amount}, New Balance: ${balance}`);
    },
    getBalance() {
      console.log(`Current Balance: ${balance}`);
    }
  };
}

const myAccount = bankAccount(100);
myAccount.deposit(50); // Deposited: 50, New Balance: 150
myAccount.getBalance(); // Current Balance: 150
```
🔹 `balance` is private and **cannot be accessed directly**.  

---

# 3️⃣ Scope vs. Closures (Key Differences)

| Feature   | Scope | Closures |
|-----------|----------------|----------------|
| **Definition** | Rules for variable access in different parts of the code | Function that remembers variables from outer scope |
| **Types** | Global, Function, Block, Lexical | Created when an inner function uses variables from an outer function |
| **Lifespan** | Variables exist as long as their scope is active | Closures preserve variables even after the outer function has executed |
| **Example** | `{ let x = 10; }` (Block scope) | `function outer() { let x = 10; return function() { console.log(x); }}` |

---

# 4️⃣ Interview Takeaways

✔ **Scope controls variable access, closures retain access to variables even after execution.**

✔ **Closures are used for data encapsulation and maintaining state.**

✔ **Lexical scope enables closures by allowing inner functions to access outer variables.**