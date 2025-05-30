# Synchronous vs Asynchronous JavaScript

## Synchronous JavaScript

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

## Asynchronous JavaScript

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