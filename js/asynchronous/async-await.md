# async/await (ES8)
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