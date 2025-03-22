# JavaScript Data Types 

JavaScript has **two categories** of data types:  

## **1️⃣ Primitive Data Types (Stored by Value, Immutable)**  
- ✅ **String** – Text enclosed in quotes (`"Hello"`)  
- ✅ **Number** – Integers & floats (`42`, `3.14`)  
- ✅ **BigInt** – Large integers (`12345678901234567890n`)  
- ✅ **Boolean** – `true` or `false`  
- ✅ **Undefined** – Variable declared but not assigned (`let x;`)  
- ✅ **Null** – Explicitly empty value (`let y = null;`)  
- ✅ **Symbol** – Unique identifier (`Symbol("id")`)
    
    ✔ Symbols are always unique (even if they have the same description).
    
    ✔ Used as object keys to prevent property conflicts.
    
    ✔ Not enumerable in loops (for...in, Object.keys()).
    
    ✔ Global Symbols (Symbol.for()) can be shared across files.
    
    ✔ Well-Known Symbols allow customization of object behavior.

---

## **2️⃣ Non-Primitive Data Types (Stored by Reference, Mutable)**  

- ✅ **Object** – Collection of key-value pairs (`{name: "Alice", age: 30}`)  
- ✅ **Array** – Ordered list of values (`[1, 2, 3]`)  
- ✅ **Function** – Block of reusable code (`function greet() {}`)

---

### **Type Conversion**

JavaScript is dynamically typed, meaning types can change.

- **Implicit Conversion (Type Coercion)**
```js
console.log("5" + 2);  // "52" (String Concatenation)
console.log("5" - 2);  // 3 (String converted to Number)
console.log(true + 1); // 2 (true is 1)
```

- **Explicit Conversion**
```js
console.log(Number("123")); // 123
console.log(String(123)); // "123"
console.log(Boolean(0)); // false
```

---

### **Checking Data Types**
Use `typeof` to check variable types.

```js
console.log(typeof "hello"); // "string"
console.log(typeof 42); // "number"
console.log(typeof true); // "boolean"
console.log(typeof undefined); // "undefined"
console.log(typeof null); // "object" (JavaScript bug)
console.log(typeof {}); // "object"
console.log(typeof []); // "object" (Arrays are objects)
console.log(typeof function(){}); // "function"
```

---

### **Key Interview Points**  
- **Primitive vs. Non-Primitive** – Primitives are immutable(cannot be changed); Non-primitives are mutable(can be changed).  
- **typeof null is `"object"`** – This is a historical bug in JavaScript.
- **`undefined` vs. `null`** – `undefined` means "not assigned", `null` means "empty value".  
- **Type Coercion** – `"5" + 2 → "52"` (String), `"5" - 2 → 3` (Number).