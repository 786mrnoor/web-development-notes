# Promises (ES6)

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