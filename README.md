# JS-Interview-Notes

If you're preparing for a JavaScript interview, here are the key areas you should focus on:

### 1. [JavaScript Fundamentals](javascript-fundamentals.md)


### **2. Advanced JavaScript**
- **ES6+ Features**: Destructuring, spread/rest operators, template literals, `let` and `const`, default parameters, etc.
- **Modules & Import/Export**: `import` vs. `require`, CommonJS vs. ES modules.
- **Event Delegation & Bubbling**: Capturing and bubbling phases in the DOM.
- **Debouncing & Throttling**: Performance optimization techniques.
- **Memory Management & Garbage Collection**: WeakMap, WeakSet, and memory leaks.
- **Currying & Partial Application**: Function transformation techniques.
- **Functional Programming Concepts**: Immutability, pure functions, recursion, etc.

### **3. Asynchronous JavaScript**
- **Promises**: `.then()`, `.catch()`, `.finally()`
- **Async/Await**: Error handling with `try/catch`
- **Microtasks & Macrotasks**: Event loop behavior
- **AJAX & Fetch API**: Making HTTP requests with `fetch()`, `XMLHttpRequest`
- **WebSockets**: Real-time communication

### **4. Object-Oriented JavaScript**
- **Constructor Functions & Classes**: ES5 vs. ES6 classes
- **Encapsulation & Polymorphism**: Getters, setters, and method overriding
- **Factory & Singleton Patterns**: Design patterns in JS

### **5. JavaScript in the Browser**
- **DOM Manipulation**: `querySelector()`, `getElementById()`, `classList`
- **Event Handling**: Event listeners, delegation
- **LocalStorage & SessionStorage**: Data persistence in the browser
- **Web APIs**: Fetch API, Geolocation API, Notification API

### **6. JavaScript for Frontend Development**
- **React.js/Vue.js/Angular**: Framework-specific knowledge
- **Virtual DOM**: How React optimizes updates
- **Component Lifecycle**: Mounting, updating, and unmounting in React

### **7. JavaScript for Backend Development**
- **Node.js Basics**: Event-driven architecture, `fs` module, `http` module
- **Express.js**: Middleware, routing, request-response lifecycle
- **Databases (MongoDB, PostgreSQL, MySQL)**: Connecting and querying databases
- **Authentication & Security**: JWT, OAuth, CSRF, CORS

### **8. Common JavaScript Interview Questions**
#### **Coding Questions**
1. **Reverse a string**  
   ```js
   function reverseString(str) {
       return str.split('').reverse().join('');
   }
   console.log(reverseString("hello")); // "olleh"
   ```

2. **Check for Palindrome**  
   ```js
   function isPalindrome(str) {
       return str === str.split('').reverse().join('');
   }
   console.log(isPalindrome("racecar")); // true
   ```

3. **Find the Largest Number in an Array**  
   ```js
   function findMax(arr) {
       return Math.max(...arr);
   }
   console.log(findMax([1, 5, 3, 9, 2])); // 9
   ```

4. **Remove Duplicates from an Array**  
   ```js
   function removeDuplicates(arr) {
       return [...new Set(arr)];
   }
   console.log(removeDuplicates([1, 2, 2, 3, 4, 4])); // [1, 2, 3, 4]
   ```

5. **Fibonacci Sequence**  
   ```js
   function fibonacci(n) {
       if (n <= 1) return n;
       return fibonacci(n - 1) + fibonacci(n - 2);
   }
   console.log(fibonacci(5)); // 5
   ```

#### **Theoretical Questions**
1. **Difference between `==` and `===`**  
   `==` checks for value equality with type coercion, whereas `===` checks for strict equality (value and type).

2. **What is a closure?**  
   A closure is a function that remembers the variables from its lexical scope even when executed outside its scope.

3. **Explain the event loop in JavaScript.**  
   The event loop allows JavaScript to handle asynchronous operations by executing callbacks in a queue after finishing synchronous code.

4. **What are promises in JavaScript?**  
   A promise is an object that represents the eventual completion (or failure) of an asynchronous operation.

5. **What is the difference between `null` and `undefined`?**  
   - `null` is an assigned value representing no value.  
   - `undefined` means a variable has been declared but not assigned a value.

Would you like me to focus on any specific area? 🚀
