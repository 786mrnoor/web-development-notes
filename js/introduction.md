# JavaScript

JavaScript is a dynamic, interpreted programming language primarily used for creating interactive and dynamic content on web pages.  
JavaScript can also be used on the server-side (Node.js).

## 1️⃣ Statement

A **statement** is an instruction that performs an action. It does not return a value.  
✅ **Examples of statements:**

- Variable declaration (`let x;`)
- Conditionals (`if`, `switch`)
- Loops (`for`, `while`)
- Function calls (`console.log("Hello");`)

🔹 **Example:**

```js
let a = 10; // Variable declaration (statement)
if (a > 5) {
  // Conditional statement
  console.log("A is greater than 5"); // Function call statement
}
```

📌 **Key Point:** Statements **do not produce a value** that can be assigned.

---

## 2️⃣ Expression

An **expression** evaluates to a value. It can be used inside other expressions or assigned to a variable.  
✅ **Examples of expressions:**

- Arithmetic: `5 + 10`
- String concatenation: `"Hello " + "World"`
- Function invocation: `Math.max(10, 20)`
- Assignment: `let b = 20;` (Right-hand side is an expression)

🔹 **Example:**

```js
let sum = 5 + 10; // Expression (5 + 10) produces a value
console.log(sum); // 15
```

📌 **Key Point:** **Expressions always return a value**.

---

## 3️⃣ Declaration

A **declaration** is a type of statement that introduces a variable, function, or class into the program.  
✅ **Examples of declarations:**

- Variable declaration (`let x;`, `const y = 10;`)
- Function declaration (`function greet() {}`)
- Class declaration (`class Person {}`)

🔹 **Example:**

```js
let name = "Alice"; // Variable declaration
function greet() {
  // Function declaration
  return "Hello!";
}
```

## 4️⃣ Parameters vs Arguments

- **Parameters** are the **placeholders** defined in a function declaration.

- **Arguments** are the actual values passed to the function when it’s called.
