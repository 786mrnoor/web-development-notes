# **Higher-Order Functions in JavaScript** 🚀  
 
- Takes **another function as an argument** (callback).  
- Returns **a function as a result**.   

---

## **Common Higher-Order Functions in JavaScript**
### **4.1 `map()`**
✔ **Transforms** each array element.  
```js
const nums = [1, 2, 3, 4];
const doubled = nums.map(n => n * 2);
console.log(doubled); // ✅ [2, 4, 6, 8]
```

### **4.2 `filter()`**
✔ **Filters** elements based on a condition.  
```js
const ages = [15, 22, 30, 12, 18];
const adults = ages.filter(age => age >= 18);
console.log(adults); // ✅ [22, 30, 18]
```

### **4.3 `reduce()`**
✔ **Accumulates** values into a single result.  
```js
const numbers2 = [1, 2, 3, 4];
const sum = numbers2.reduce((acc, num) => acc + num, 0);
console.log(sum); // ✅ Output: 10
```

### **4.4 `forEach()`**
✔ **Iterates** over an array (no return).  
```js
const fruits = ["🍎", "🍌", "🍇"];
fruits.forEach(fruit => console.log(fruit));
```

---

## **6️⃣ Summary**
✔ **Higher-Order Functions** take a function as an argument or return a function.  
✔ Examples: `map()`, `filter()`, `reduce()`, `forEach()`.  
✔ Makes code **cleaner, reusable, and functional**.  