# async/await

`async` and `await` keywords are used for managing asynchronous operations in a more readable and structured way. 

- `async` makes a function return a **Promise**.  
- `await` **pauses** the function execution until the promise is fulfilled.  

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

## Error handling with `try/catch`

Error handling in `async/await` code is done using `try...catch` blocks. Any error occurs within the `try` block will be caught by the `catch` block. 

```js
async function fetchData() {
  try {
    const response = await fetch('https://example.com/data');
    const data = await response.json();
    return data;
  }
  catch (error) {
    console.error('Error fetching data:', error);
    return null; // or handle the error in a more appropriate way
  }
}
```