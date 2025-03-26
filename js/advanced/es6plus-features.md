# **ES6+ Features (Modern JavaScript) - Interview Guide** 🚀  

ES6 (ECMAScript 2015) and later versions introduced powerful features that improve JavaScript code efficiency, readability, and maintainability.  

---

## **1️⃣ Arrow Functions (=>)**
- **Arrow functions provide a cleaner and shorter syntax.**
- They inherit `this` from the surrounding scope.
- They dDo not support `arguments`, `super`, and `new` keyword.
- Avoid in object methods & constructors.

---

## **2️⃣ Template Literals (\` `)**
- Templates literals are strings enclosed in backticks (\``This is a template string`\`).
- It support multi-line strings & variable interpolation.
- Templates allow single and double quotes inside a string:

🔹 **Example:**
```js
let name = "Alice";
console.log(`Hello, ${name}!`); // ✅ Hello, Alice!
```

---

## **3️⃣ Destructuring (Arrays & Objects)**
- It is used to unpack `object` and `arrays` properties into variables:  

🔹 **Array Destructuring:**
```js
const numbers = [10, 20, 30];
const [a, b] = numbers; // ✅ a = 10, b = 20
```

🔹 **Object Destructuring:**
```js
const person = { name: "John", age: 25 };
const { name, age } = person; // ✅ name = "John", age = 25
```

---

## **4️⃣ Spread & Rest Operators (`...`)**
### **4.1 Spread Operator (`...`)**
- Expands `arrays` and `objects` into individual elements.  

🔹 **Example:**
```js
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5]; // ✅ [1, 2, 3, 4, 5]

const obj1 = { a: 1, b: 2 };
const obj2 = { ...obj1, c: 3 }; // ✅ { a: 1, b: 2, c: 3 }
```

### **4.2 Rest Operator (`...`)**
- Gathers multiple arguments into an array.
-  It is used in function parameter lists to collect the remaining or indefinite number of arguments into an array. 

🔹 **Example:**
```js
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3, 4)); // ✅ 10
```

---

## **5️⃣ Default Parameters**
- Set default values for function parameters.  

🔹 **Example:**
```js
function greet(name = "Guest") {
  console.log(`Hello, ${name}`);
}
greet(); // ✅ Hello, Guest
greet("Alice"); // ✅ Hello, Alice
```

---

## **6️⃣ Optional Chaining (`?.`)**
- Avoids errors when accessing nested properties.  

🔹 **Example:**
```js
const user = { profile: { name: "Alice" } };
console.log(user.profile?.name); // ✅ Alice
console.log(user.address?.city); // ✅ undefined (No error)
```

---

## **7️⃣ Nullish Coalescing (`??`)**
- Returns the **right-hand value only if the left-hand value is `null` or `undefined`**.  

🔹 **Example:**
```js
let value = null;
console.log(value ?? "Default"); // ✅ Default

value = 0;
console.log(value ?? "Default"); // ✅ 0 (Because 0 is not null/undefined)
```

---

## **Interview Takeaways 🎯**
✔ **Arrow functions provide shorter syntax & lexical `this`.**  
✔ **Destructuring & spread/rest make working with objects/arrays easier.**  
✔ **Optional chaining (`?.`) prevents unnecessary errors.** 