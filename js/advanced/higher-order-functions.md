# **Higher-Order Functions in JavaScript** 🚀  
 
- Takes **another function as an argument** (callback).  
- Returns **a function as a result**.   

---

## **Common Higher-Order Functions in JavaScript**
### **`map()`**
✔ **Transforms** each array element.  
```js
const nums = [1, 2, 3, 4];
const doubled = nums.map(n => n * 2);
console.log(doubled); // ✅ [2, 4, 6, 8]
```

### **`filter()`**
✔ **Filters** elements based on a condition.  
```js
const ages = [15, 22, 30, 12, 18];
const adults = ages.filter(age => age >= 18);
console.log(adults); // ✅ [22, 30, 18]
```

### **`reduce()`**
✔ **Accumulates** values into a single result.  
```js
const numbers2 = [1, 2, 3, 4];
const sum = numbers2.reduce((acc, num) => acc + num, 0);
console.log(sum); // ✅ Output: 10
```

### **`forEach()`**
✔ **Iterates** over an array (no return).  
```js
const fruits = ["🍎", "🍌", "🍇"];
fruits.forEach(fruit => console.log(fruit));
```

---
### **`sort()`**
✔ The `sort()` method sorts the elements of an array in place(modifies original array) and returns the sorted array. 

```js
const numbers = [25, 5, 100, 40];
numbers.sort(); 
console.log(numbers); 
// ❌ Output: [100, 25, 40, 5] (Sorted as strings)
```
✔ Why? sort() treats numbers as strings ("100" < "25" in string comparison).

**To sort numbers correctly, use a compare function:**
```js
const numbers = [25, 5, 100, 40];

// Ascending order
numbers.sort((a, b) => a - b);
console.log(numbers); 
// ✅ Output: [5, 25, 40, 100]

// Descending order
numbers.sort((a, b) => b - a);
console.log(numbers); 
// ✅ Output: [100, 40, 25, 5]
```
- A negative value indicates that `a` should come before `b`.
- A positive value indicates that `a` should come after `b`.
- `Zero` or `NaN` indicates that `a` and `b` are considered equal.

---

## **6️⃣ Summary**
✔ **Higher-Order Functions** take a function as an argument or return a function.  
✔ Examples: `map()`, `filter()`, `reduce()`, `forEach()` and `sort`.  
✔ Makes code **cleaner, reusable, and functional**.  