# **Constructor Functions & Classes in JavaScript (ES5 vs. ES6)** 🚀  

JavaScript provides two ways to create objects using **constructors**:  
1. **ES5 Constructor Functions** (older, function-based)  
2. **ES6 Classes** (modern, class-based)  

---

## **1️⃣ Constructor Functions (ES5)**
A constructor function in JavaScript is used to create objects. It defines the properties and methods that an object of that type will have. Constructor functions are called using the `new` keyword. By convention, constructor functions are named starting with a capital letter.

 **constructor functions**.

🔹 **Example: ES5 Constructor Function**
```js
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function () {
  return `Hello, my name is ${this.name}.`;
};

const alice = new Person("Alice", 25);
console.log(alice.greet()); // ✅ Output: Hello, my name is Alice.
```
✔ Uses **prototype** to define methods.  
✔ Uses `new` keyword to create an instance.  

---

## **2️⃣ ES6 Classes**
ES6 introduced the `class` keyword, which makes object-oriented programming **cleaner and more readable**.

A class in JavaScript is a blueprint for creating objects. It encapsulates data and methods that operate on that data within a single unit.

JavaScript classes are syntactic sugar over the prototype-based inheritance model, meaning they are built on top of prototypes.

🔹 **Example: ES6 Class**
```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    return `Hello, my name is ${this.name}.`;
  }
}

const bob = new Person("Bob", 30);
console.log(bob.greet()); // ✅ Output: Hello, my name is Bob.
```
✔ More **readable** and **structured** than constructor functions.  
✔ Methods are **automatically added to the prototype**.  

---


## **3️⃣ Inheritance in ES5 vs. ES6**
### **🔹 ES5 Prototype-Based Inheritance**
```js
function Employee(name, salary) {
  Person.call(this, name);
  this.salary = salary;
}

Employee.prototype = Object.create(Person.prototype);
Employee.prototype.constructor = Employee;

Employee.prototype.getSalary = function () {
  return `My salary is $${this.salary}`;
};

const emp1 = new Employee("Alice", 5000);
console.log(emp1.greet()); // ✅ "Hello, my name is Alice."
console.log(emp1.getSalary()); // ✅ "My salary is $5000"
```

### **🔹 ES6 Class-Based Inheritance**
```js
class Employee extends Person {
  constructor(name, salary) {
    super(name); // Calls parent constructor
    this.salary = salary;
  }

  getSalary() {
    return `My salary is $${this.salary}`;
  }
}

const emp2 = new Employee("Bob", 6000);
console.log(emp2.greet()); // ✅ "Hello, my name is Bob."
console.log(emp2.getSalary()); // ✅ "My salary is $6000"
```
✔ `extends` makes inheritance easier.  
✔ `super()` calls the **parent constructor**.  

---

## **4️⃣ Summary**
✔ **Constructor Functions (ES5)** → Use **function-based prototype inheritance**.  
✔ **Classes (ES6)** → Provide a **cleaner, more readable** way to create objects.  
✔ **ES6 Classes use `extends` & `super`** for easier inheritance.  