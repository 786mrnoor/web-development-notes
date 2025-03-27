# **Factory & Singleton Patterns in JavaScript** 🚀  

JavaScript supports various **design patterns** to organize code efficiently.  
Two important patterns are:  
1. **Factory Pattern** 🏭 → A function that creates objects without using `new`.  
2. **Singleton Pattern** 🔁 → Ensures only **one** instance of an object exists.  

---

## **1️⃣ Factory Pattern (Object Creation Without `new`)**  

The **Factory Pattern** is a function that **returns new objects** without using `new`.  
- It provides **flexibility** in object creation.  
- Useful when creating **multiple objects** with similar properties but **different values**.  

### **🔹 Example: Factory Function**
```js
function createPerson(name, age) {
  return {
    name,
    age,
    greet() {
      return `Hello, my name is ${this.name}.`;
    }
  };
}

const person1 = createPerson("Alice", 25);
const person2 = createPerson("Bob", 30);

console.log(person1.greet()); // ✅ "Hello, my name is Alice."
console.log(person2.greet()); // ✅ "Hello, my name is Bob."
```
✔ The function **returns objects dynamically** without `new`.  

---

### **🔹 Factory Pattern with Encapsulation**
Encapsulation helps protect object properties.

```js
function createCar(brand, model) {
  let _mileage = 0; // Private variable

  return {
    brand,
    model,
    drive(km) {
      _mileage += km;
      console.log(`${brand} ${model} drove ${km} km.`);
    },
    getMileage() {
      return `Mileage: ${_mileage} km`;
    }
  };
}

const myCar = createCar("Tesla", "Model 3");
myCar.drive(100);
console.log(myCar.getMileage()); // ✅ Mileage: 100 km
console.log(myCar._mileage); // ❌ Undefined (Encapsulation)
```
✔ `_mileage` is **private** due to closure.  

---

## **2️⃣ Singleton Pattern (One Instance Only)**  

The **Singleton Pattern** ensures that a class **has only one instance** and provides a **global access point**.  
- Useful for **caching, configuration settings, and managing shared states**.  

### **🔹 Example: Basic Singleton**
```js
const Singleton = (function () {
  let instance; // Private variable to store instance

  function createInstance() {
    return { message: "I am the only instance!" };
  }

  return {
    getInstance() {
      if (!instance) {
        instance = createInstance();
      }
      return instance;
    }
  };
})();

const obj1 = Singleton.getInstance();
const obj2 = Singleton.getInstance();

console.log(obj1 === obj2); // ✅ true (Same instance)
console.log(obj1.message); // ✅ "I am the only instance!"
```
✔ `Singleton.getInstance()` always returns the **same instance**.  

---

### **🔹 Singleton with ES6 Class**
```js
class Database {
  constructor() {
    if (Database.instance) {
      return Database.instance; // Return existing instance
    }
    this.connection = "Connected to Database";
    Database.instance = this; // Store instance
  }

  getConnection() {
    return this.connection;
  }
}

const db1 = new Database();
const db2 = new Database();

console.log(db1 === db2); // ✅ true (Same instance)
console.log(db1.getConnection()); // ✅ "Connected to Database"
```
✔ The class **remembers the first instance** and returns it.  

---

## **3️⃣ Factory vs. Singleton: Key Differences**  

| Feature         | Factory Pattern 🏭 | Singleton Pattern 🔁 |
|---------------|----------------|----------------|
| **Purpose**   | Creates multiple instances | Ensures only one instance |
| **Usage**     | Flexible object creation | Shared state or configuration |
| **Encapsulation** | Can encapsulate properties | Shared across the app |
| **Implementation** | Returns a new object each time | Returns the same object |

---

## **4️⃣ Summary**
✔ **Factory Pattern** → Creates **multiple objects** with encapsulated properties.  
✔ **Singleton Pattern** → Ensures **only one instance** exists.  
✔ **Use Factory** for **dynamic object creation**.  
✔ **Use Singleton** when **only one instance is needed**.  