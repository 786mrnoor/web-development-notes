# **Debouncing & Throttling in JavaScript** 🚀  

## **Debouncing**
**Debouncing** ensures a function **executes only after a delay** once the event stops triggering.  

🔹 **Example: Delaying API Call in Search Input**
```js
function debounce(func, delay) {
  let timer;
  return function (...args) {
    clearTimeout(timer);
    timer = setTimeout(() => func.apply(this, args), delay);
  };
}

// Simulating API call
function fetchResults(query) {
  console.log("Fetching results for:", query);
}

const searchInput = document.querySelector("#search");
searchInput.addEventListener("input", debounce((e) => fetchResults(e.target.value), 500));
```
✅ **Why Use Debounce?**  
✔ Prevents **unnecessary API calls** while typing in a search bar.  
✔ Executes **only after** typing **stops for 500ms**.  

---

## **Throttling**
**Throttling** ensures a function **executes at most once per time interval**, even if triggered multiple times.  

🔹 **Example: Throttling Scroll Event**
```js
function throttle(fn, delay) {
    let ignore = false;

    return function (...args) {
        if (ignore) return;
        fn.apply(this, args);
        ignore = true;

        setTimeout(() => {
            ignore = false;
        }, delay);
    };
}

window.addEventListener('scroll', throttle(() => {
    console.log('Scroll event triggered!');
}, 1000));
```
✅ **Why Use Throttle?**  
✔ Prevents **too many function calls** while scrolling.  
✔ Limits execution to **once every 200ms**.  

---

## **When to Use Debounce vs. Throttle?**
✔ **Debounce** → **Waits for inactivity**, best for **input fields, resizing**.  
✔ **Throttle** → **Runs at intervals**, best for **scrolling, button clicks**.  