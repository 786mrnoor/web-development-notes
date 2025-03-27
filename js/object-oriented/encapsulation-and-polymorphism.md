# **Encapsulation & Polymorphism in JavaScript** 🚀  

Encapsulation and Polymorphism are key concepts of **Object-Oriented Programming (OOP)** in JavaScript.

---

## **1️⃣ Encapsulation: Data Hiding with Getters & Setters**  
Encapsulation is the practice of **restricting direct access** to object properties and allowing controlled access through **getters and setters**.

🔹 **Example: Using Getters & Setters in ES6 Classes**
```js
class Person {
  constructor(name, age) {
    this._name = name; // Underscore to indicate private property
    this._age = age;
  }

  // Getter method
  get age() {
    return this._age;
  }

  // Setter method
  set age(value) {
    if (value < 0) {
      console.log("Age cannot be negative!");
    } else {
      this._age = value;
    }
  }
}

const person = new Person("Alice", 25);
console.log(person.age); // ✅ 25 (calls getter)
person.age = -5;        // ❌ Age cannot be negative!
person.age = 30;
console.log(person.age); // ✅ 30 (calls setter)
```
✔ Getters **retrieve values** securely.  
✔ Setters **validate values** before updating.  

---

## **2️⃣ Private Fields in JavaScript (ES2020+)**  
JavaScript introduced **true private fields** using `#` to prevent direct access.

🔹 **Example: Private Fields**
```js
class BankAccount {
  #balance; // Private field

  constructor(initialAmount) {
    this.#balance = initialAmount;
  }

  deposit(amount) {
    this.#balance += amount;
  }

  getBalance() {
    return this.#balance;
  }
}

const account = new BankAccount(1000);
account.deposit(500);
console.log(account.getBalance()); // ✅ 1500
console.log(account.#balance); // ❌ Error: Private field not accessible
```
✔ The `#balance` property **cannot** be accessed outside the class.  

---

## **3️⃣ Polymorphism: Method Overriding**  
Polymorphism allows a **subclass** to **override** methods from a parent class.

🔹 **Example: Method Overriding in ES6 Classes**
```js
class Animal {
  speak() {
    return "This animal makes a sound.";
  }
}

class Dog extends Animal {
  speak() {
    return "Woof! Woof!";
  }
}

class Cat extends Animal {
  speak() {
    return "Meow! Meow!";
  }
}

const dog = new Dog();
const cat = new Cat();

console.log(dog.speak()); // ✅ Output: "Woof! Woof!"
console.log(cat.speak()); // ✅ Output: "Meow! Meow!"
```
✔ The `speak()` method is **overridden** in `Dog` and `Cat`.  

---

## **4️⃣ Using `super` to Call Parent Methods**
The `super` keyword allows calling **methods from the parent class**.

🔹 **Example: Overriding with `super`**
```js
class Vehicle {
  move() {
    return "This vehicle is moving.";
  }
}

class Car extends Vehicle {
  move() {
    return super.move() + " 🚗 Vroom!";
  }
}

const car = new Car();
console.log(car.move()); // ✅ Output: "This vehicle is moving. 🚗 Vroom!"
```
✔ `super.move()` calls the **parent class method**.  

---

## **5️⃣ Summary**
✔ **Encapsulation** → Hides data using **getters, setters, and private fields (`#`)**.  
✔ **Polymorphism** → Allows **method overriding** for flexible behavior.  
✔ **`super` keyword** → Calls parent methods inside overridden methods.  