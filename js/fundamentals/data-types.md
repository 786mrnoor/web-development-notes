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

---

## **2️⃣ Non-Primitive Data Types (Stored by Reference, Mutable)**  

- ✅ **Object** – Collection of key-value pairs (`{name: "Alice", age: 30}`)  
- ✅ **Array** – Ordered list of values (`[1, 2, 3]`)  
- ✅ **Function** – Block of reusable code (`function greet() {}`)

---

## Key Interview Points  
- **Primitive vs. Non-Primitive** – Primitives are immutable; Non-primitives are mutable.  
- **typeof null is `"object"`** – This is a historical bug in JavaScript.
- **`undefined` vs. `null`** – `undefined` means "not assigned", `null` means "empty value".  
- **Type Coercion** – `"5" + 2 → "52"` (String), `"5" - 2 → 3` (Number).