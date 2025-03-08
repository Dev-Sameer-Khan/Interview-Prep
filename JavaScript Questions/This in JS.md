# How `this` Works in JavaScript

The `this` keyword in JavaScript refers to **the object that is executing the current function**. Its value depends on how and where the function is called.

## 1️⃣ `this` in the Global Context
- In the **browser**, `this` refers to the `window` object.
- In **strict mode**, `this` is `undefined`.

```js
console.log(this); // window (in browser)
'use strict';
console.log(this); // undefined
```

## 2️⃣ `this` in an Object Method
- When used inside an **object method**, `this` refers to that object.

```js
const person = {
  name: "Sameer",
  greet: function() {
    console.log(this.name);
  }
};
person.greet(); // "Sameer"
```

## 3️⃣ `this` in a Constructor Function
- Inside a **constructor function**, `this` refers to the newly created object.

```js
function Person(name) {
  this.name = name;
}
const user = new Person("Sameer");
console.log(user.name); // "Sameer"
```

## 4️⃣ `this` in an Arrow Function
- **Arrow functions** do not have their own `this`; they inherit `this` from their surrounding scope.

```js
const obj = {
  name: "Sameer",
  greet: () => {
    console.log(this.name);
  }
};
obj.greet(); // undefined (inherits `this` from global scope)
```

## 5️⃣ `this` in an Event Listener
- In an **event listener**, `this` refers to the element that fired the event.

```js
document.getElementById("btn").addEventListener("click", function() {
  console.log(this); // Refers to the button element
});
```

## 🔥 Summary
| Context | `this` Refers To |
|---------|-----------------|
| Global Scope | `window` (or `undefined` in strict mode) |
| Object Method | The object itself |
| Constructor Function | The new instance |
| Arrow Function | `this` of the surrounding scope |
| Event Listener | The element that triggered the event |

🚀 Understanding `this` is **crucial** for writing clean and efficient JavaScript code!

