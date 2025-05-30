# Event Loop

JavaScript is **single-threaded**, meaning it can execute **one operation at a time**. However, it uses the **Event Loop** to handle asynchronous tasks like API calls, setTimeout, and event listeners efficiently.

## How the Event Loop Works?

The **Event Loop** has **three main parts**:  

1. **Call Stack**
2. **Web APIs**
3. **Queues: Microtask Queue** or **Callback Queue(Macrotask)**  

**The Event Loop continuously monitors theses parts**
1. **Call Stack** executes synchronous code.  
2. When encountering asynchronous tasks (e.g., `setTimeout`, `fetch`), they move to **Web APIs** (handled by the browser).  
3. Once completed, the callback moves to either the **Microtask Queue** (for `Promises`) or the **Callback Queue** (for `setTimeout`, `setInterval`).  
4. The **Event Loop** moves tasks from these queues to the Call Stack when it is empty.  

---

## Microtask Queue vs. Callback(Macrotask) Queue
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