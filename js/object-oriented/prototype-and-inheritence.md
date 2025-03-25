# **Prototype & Inheritance in JavaScript** 🚀  

JavaScript uses **prototypal inheritance**, which allows objects to inherit properties and methods from other objects through the **prototype chain**.  

---

## **1️⃣ What is a Prototype?**  
In JavaScript, every object has an internal reference to another object called its **prototype**.  
- If a property or method **is not found** on an object, JavaScript looks **up the prototype chain**.  

🔹 **Example: Checking Prototype**
```js
const obj = {};
console.log(Object.getPrototypeOf(obj)); // ✅ Outputs: {} (Object.prototype)
```

---

## **2️⃣ Prototype Chain**
When you access a property on an object:
1. JavaScript **first checks** if the property exists on the object.  
2. If **not found**, it moves **up the prototype chain** to the object's prototype.  
3. This process continues until it reaches `Object.prototype`, which is the top of the chain.  

🔹 **Example: Prototype Chain in Action**
```js
const person = {
  greet() {
    return "Hello!";
  }
};

const student = Object.create(person); // student inherits from person
console.log(student.greet()); // ✅ Output: "Hello!" (from prototype)
```
✔ Since `greet` is not found on `student`, it looks **up the prototype chain**.

---

## **3️⃣ Constructor Functions & Prototypes**
Every function in JavaScript has a `prototype` property, which is used when creating new objects.

🔹 **Example: Adding Methods to a Prototype**
```js
function Person(name) {
  this.name = name;
}

// Adding a method to the prototype
Person.prototype.greet = function () {
  return `Hello, my name is ${this.name}.`;
};

const alice = new Person("Alice");
console.log(alice.greet()); // ✅ Output: "Hello, my name is Alice."
console.log(alice.__proto__ === Person.prototype); // ✅ true
```
✔ The method `greet()` is stored in the **prototype**, not in each instance.

---

## **4️⃣ Class-Based Inheritance (ES6)**
With **ES6 Classes**, prototype-based inheritance is more readable.

🔹 **Example: Class Inheritance**
```js
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    return `${this.name} makes a sound.`;
  }
}

class Dog extends Animal {
  speak() {
    return `${this.name} barks.`;
  }
}

const dog = new Dog("Buddy");
console.log(dog.speak()); // ✅ Output: "Buddy barks."
```
✔ `Dog` **inherits** from `Animal` using `extends`.  
✔ `super()` calls the **parent class constructor**.  

---

## **5️⃣ Checking Prototype Inheritance**
### **Using `isPrototypeOf`**
```js
console.log(Animal.prototype.isPrototypeOf(dog)); // ✅ true
```
✔ Checks if `Animal.prototype` is in `dog`'s prototype chain.

### **Using `instanceof`**
```js
console.log(dog instanceof Dog); // ✅ true
console.log(dog instanceof Animal); // ✅ true
console.log(dog instanceof Object); // ✅ true
```
✔ `dog` is an instance of **both** `Dog` and `Animal` due to inheritance.

---

## **6️⃣ Summary**
✔ **Prototype Chain** → Objects inherit properties from prototypes.  
✔ **Constructor Functions** → Use `.prototype` to share methods.  
✔ **ES6 Classes** → Provide a cleaner syntax for inheritance.  
✔ **Checking Prototype** → Use `instanceof`, `isPrototypeOf`, or `Object.getPrototypeOf()`. 