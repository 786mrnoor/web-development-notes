# Advanced JavaScript

- [**ES6+ Features:**](es6plus-features.md)  Arrow Functions, template literals, Destructuring, spread & rest operators, default parameters, optional chaining and nullish coalescing.

- [**Modules & Import/Export:**](modules.md)
 
- [**Higher-Order Functions:**](higher-order-functions.md) `map()`, `filter()`, `reduce()`, `sort()`, etc.

- [**Event Delegation & Bubbling:**](event-delefation-and-bubbling.md) Capturing and bubbling phases in the DOM.

- [**Debouncing & Throttling:**](debounce-and-throttling.md) Performance optimization techniques.

- **Recursion**: Recursion is when a function calls itself until a base condition is met.
```js
function factorial(n) {
  if (n === 1) return 1; // Base case
  return n * factorial(n - 1);
}
console.log(factorial(5)); // ✅ Output: 120
```