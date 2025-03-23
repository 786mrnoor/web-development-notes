# Event Loop & Asynchronous JavaScript  

JavaScript is **single-threaded**, meaning it can execute **one operation at a time**. However, it uses the **Event Loop** to handle asynchronous tasks like API calls, setTimeout, and event listeners efficiently.

---

## 1️⃣ Synchronous vs Asynchronous JavaScript

### **Synchronous JavaScript**

- Executes code **line by line**.  
- Blocks further execution until the current task is complete.  

```js
console.log("Start");
for (let i = 0; i < 3; i++) {
  console.log(i);
}
console.log("End");

// Output:
// Start
// 0
// 1
// 2
// End
```

### **Asynchronous JavaScript**

- Uses **callbacks, promises, and async/await** to run tasks **without blocking** execution.  
- The **Event Loop** manages asynchronous tasks in the background.  

```js
console.log("Start");

setTimeout(() => {
  console.log("Delayed Task");
}, 2000);

console.log("End");

// Output:
// Start
// End
// (After 2 seconds) Delayed Task
```

---

## 2️⃣ How the Event Loop Works?

The **Event Loop** manages execution in **two main parts**:  

1. **Call Stack** (Handles synchronous code)  
2. **Callback Queue(Macrotask) & Microtask Queue** (Handles asynchronous code)  

### **Execution Order**
1. **Call Stack** executes synchronous code.  
2. When encountering asynchronous tasks (e.g., `setTimeout`, `fetch`), they move to **Web APIs** (handled by the browser).  
3. Once completed, the callback moves to either the **Microtask Queue** (for Promises & async/await) or the **Callback Queue** (for `setTimeout`, `setInterval`).  
4. The **Event Loop** moves tasks from these queues to the Call Stack when it is empty.  

---

## 3️⃣ Microtask Queue vs. Callback(Macrotask) Queue
- **Microtask Queue** has higher priority (used for `Promises` & `async/await`).  
- **Callback Queue** has lower priority (used for `setTimeout`, `setInterval`).  

🔹 **Example:**  
```js
console.log("Start");

setTimeout(() => console.log("Timeout"), 0);

Promise.resolve().then(() => console.log("Promise"));

console.log("End");

// Output:
// Start
// End
// Promise  ✅ (Microtask runs before setTimeout)
// Timeout
```

---

## 4️⃣ Promises & async/await
### **4.1 Promises (ES6)**
A **Promise** represents a value that will be available in the future.  
It has three states:
- **Pending** → Initial state  
- **Resolved (Fulfilled)** → Operation successful  
- **Rejected** → Operation failed  

```js
let promise = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Data received!"), 2000);
});

promise.then(response => console.log(response));
```

---

### **4.2 async/await (ES8)**
- `async` makes a function return a **Promise**.  
- `await` **pauses** execution until the Promise resolves.  

```js
async function fetchData() {
  console.log("Fetching...");
  let data = await new Promise((resolve) =>
    setTimeout(() => resolve("Data Loaded"), 2000)
  );
  console.log(data);
}

fetchData();
```

**Output:**
```
Fetching...
(After 2 seconds)
Data Loaded
```

---

## **5️⃣ Interview Takeaways**
✔ **JavaScript uses the Event Loop to handle asynchronous tasks efficiently.**  
✔ **Microtask Queue (Promises, async/await) runs before the Callback Queue (setTimeout).**  
✔ **async/await simplifies handling asynchronous operations using Promises.**  
✔ **setTimeout with `0ms` still runs after all synchronous code & microtasks.**