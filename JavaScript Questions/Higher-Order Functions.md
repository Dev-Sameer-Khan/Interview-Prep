# Higher-Order Functions in JavaScript

## 🔥 What is a Higher-Order Function?
A **higher-order function** is a function that either:
- Takes another function as an **argument**.
- **Returns** a function.

This helps in making code **more reusable and modular**.

---

## ✅ Example 1: Function Taking Another Function as an Argument
```js
function greet(name, callback) {
    console.log("Hello, " + name);
    callback();
}

function sayBye() {
    console.log("Goodbye!");
}

greet("John", sayBye);
```
**Output:**
```
Hello, John
Goodbye!
```

---

## ✅ Example 2: Function Returning Another Function
```js
function multiplyBy(factor) {
    return function (num) {
        return num * factor;
    };
}

const double = multiplyBy(2);
console.log(double(5)); // Output: 10
```

---

## 🏆 Why Use Higher-Order Functions?
✅ **Code Reusability** – Makes functions more generic and flexible.
✅ **Cleaner Code** – Reduces redundant code.
✅ **Better Function Composition** – Helps in functional programming.

🚀 **Common Examples:** `map()`, `filter()`, `reduce()` in JavaScript are all higher-order functions!
```js
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(num => num * 2);
console.log(doubled); // Output: [2, 4, 6, 8]
```

Higher-order functions make JavaScript **more powerful and expressive**!

