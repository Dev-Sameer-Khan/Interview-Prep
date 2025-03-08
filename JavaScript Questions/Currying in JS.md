# Currying in JavaScript

## 🔥 What is Currying?
**Currying** is a technique in JavaScript where a function takes **multiple arguments one at a time**, instead of all at once. It helps in **reusability** and **function composition**.

---

## ✅ Syntax:
```js
function curry(a) {
    return function (b) {
        return function (c) {
            return a + b + c;
        };
    };
}

console.log(curry(2)(3)(4)); // Output: 9
```

---

## 🚀 Why Use Currying?
✅ **Code Reusability** – Breaks functions into smaller reusable parts.
✅ **Avoids Repetition** – Helps in reducing redundant code.
✅ **Function Composition** – Makes complex functions easier to manage.

---

## ✅ Example 1: Traditional Function vs. Curried Function
### 🎯 Without Currying:
```js
function add(a, b, c) {
    return a + b + c;
}
console.log(add(2, 3, 4)); // Output: 9
```

### 🎯 With Currying:
```js
const addCurried = a => b => c => a + b + c;
console.log(addCurried(2)(3)(4)); // Output: 9
```

---

## ✅ Example 2: Practical Use in Function Composition
```js
const multiply = a => b => a * b;
const double = multiply(2);
console.log(double(5)); // Output: 10
```

---

## 🔥 Best Practices
✔️ Use currying when dealing with **partial applications**.
✔️ Helps in **functional programming**.
✔️ Modern libraries like **Lodash** provide built-in currying functions.

