## **8. Common JavaScript Interview Questions**
#### **Coding Questions**
1. **Reverse a string**  
   ```js
   function reverseString(str) {
       return str.split('').reverse().join('');
   }
   console.log(reverseString("hello")); // "olleh"
   ```

2. **Check for Palindrome**  
   ```js
   function isPalindrome(str) {
       return str === str.split('').reverse().join('');
   }
   console.log(isPalindrome("racecar")); // true
   ```

3. **Find the Largest Number in an Array**  
   ```js
   function findMax(arr) {
       return Math.max(...arr);
   }
   console.log(findMax([1, 5, 3, 9, 2])); // 9
   ```

4. **Remove Duplicates from an Array**  
   ```js
   function removeDuplicates(arr) {
       return [...new Set(arr)];
   }
   console.log(removeDuplicates([1, 2, 2, 3, 4, 4])); // [1, 2, 3, 4]
   ```

5. **Fibonacci Sequence**  
   ```js
   function fibonacci(n) {
       if (n <= 1) return n;
       return fibonacci(n - 1) + fibonacci(n - 2);
   }
   console.log(fibonacci(5)); // 5
   ```

#### **Theoretical Questions**
1. **Difference between `==` and `===`**  
   `==` checks for value equality with type coercion, whereas `===` checks for strict equality (value and type).

2. **What is a closure?**  
   A closure is a function that remembers the variables from its lexical scope even when executed outside its scope.

3. **Explain the event loop in JavaScript.**  
   The event loop allows JavaScript to handle asynchronous operations by executing callbacks in a queue after finishing synchronous code.

4. **What are promises in JavaScript?**  
   A promise is an object that represents the eventual completion (or failure) of an asynchronous operation.

5. **What is the difference between `null` and `undefined`?**  
   - `null` is an assigned value representing no value.  
   - `undefined` means a variable has been declared but not assigned a value.

Would you like me to focus on any specific area? 🚀
