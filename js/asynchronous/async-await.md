# async/await

`async` and `await` are keywords used for managing asynchronous operations in a more readable and structured way. 

- `async` makes a function return a **Promise**.  
- `await` **pauses** execution until the promise is fulfilled.  

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