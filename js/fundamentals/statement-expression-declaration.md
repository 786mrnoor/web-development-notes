
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
if (a > 5) {  // Conditional statement
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
console.log(sum);  // 15
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
function greet() {  // Function declaration
  return "Hello!";
}
```
📌 **Key Point:** Declarations **introduce new identifiers** into the program.

---

### **Comparison Table**
| Feature              | Statement          | Expression       | Declaration                               |
| -------------------- | ------------------ | ---------------- | ----------------------------------------- |
| **Purpose**          | Performs an action | Produces a value | Introduces a variable, function, or class |
| **Returns Value?**   | ❌ No               | ✅ Yes            | ❌ No                                      |
| **Example**          | `if (x > 10) {}`   | `5 + 3`          | `let x = 5;`                              |
| **Can be assigned?** | ❌ No               | ✅ Yes            | ❌ No                                      |

---

### **Key Interview Takeaways**
✔ **Statements** perform actions but do not return values.  
✔ **Expressions** return values and can be assigned to variables.  
✔ **Declarations** introduce variables, functions, or classes.  