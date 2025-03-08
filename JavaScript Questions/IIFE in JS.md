# IIFE (Immediately Invoked Function Expression) in JavaScript

## 🔥 What is an IIFE?
An **IIFE (Immediately Invoked Function Expression)** is a JavaScript function that executes **immediately** after it is defined.

### ✅ Syntax:
```js
(function () {
    console.log("This runs immediately!");
})();
```

---

## 🚀 Why Use an IIFE?
✅ **Avoids Global Scope Pollution** – Variables inside an IIFE are **private**.
✅ **Runs Code Immediately** – Useful for initialization.
✅ **Encapsulates Code** – Prevents conflicts with other scripts.

---

## ✅ Example 1: Simple IIFE
```js
(function () {
    let message = "Hello from IIFE!";
    console.log(message);
})();
```
**Output:**
```
Hello from IIFE!
```

---

## ✅ Example 2: IIFE with Parameters
```js
(function (name) {
    console.log("Hello, " + name + "!");
})("John");
```
**Output:**
```
Hello, John!
```

---

## ✅ Example 3: Arrow Function IIFE
```js
(() => {
    console.log("Arrow function IIFE!");
})();
```

---

## 🔥 Best Practices
✔️ Use **IIFE** when you need an **isolated scope**.
✔️ Helps in **modularizing** code in older JavaScript versions.
✔️ **ES6 Modules** have mostly replaced IIFEs for scoping.

