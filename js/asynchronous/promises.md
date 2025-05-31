# Promises (ES6)

A **Promise** represents a value that will be available in the future.
It has three states:
- **Pending** → Initial state, neither fulfilled nor rejected.
- **Fulfilled** → Operation successful.
- **Rejected** → Operation failed.

```js
let myPromise = new Promise((resolve, reject) => {
  let result = true; // Simulate an asynchronous operation

  if (result) {
    resolve("Success!");
  } else {
    reject("Error!");
  }
});
```

## Promise methods
- `.then()`: Used to handle the fulfilled state of a promise. It takes up to two arguments, the first argument is a callback function for the fulfilled case of the promise, and the second argument is a callback function for the rejected case.
- `.catch()`: Used to handle the rejected state of a promise. It takes a callback function that will be executed when the promise is rejected.
- `.finally()`: Used to execute code regardless of whether the promise is fulfilled or rejected. 

```js
myPromise
  .then((message) => {
    console.log(message); // Output: "Success!"
  })
  .catch((error) => {
    console.error(error); // Output: "Error!"
  })
  .finally(() => {
    console.log("Promise completed.");
  });
```