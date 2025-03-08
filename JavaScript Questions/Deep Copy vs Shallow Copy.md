# Deep Copy vs Shallow Copy in JavaScript

## 🔥 What is the Difference?
Deep Copy and Shallow Copy are ways to copy objects or arrays in JavaScript.

| Type | Definition | Example |
|------|------------|---------|
| **Shallow Copy** | Copies only references of nested objects, not the actual objects. Changes in the original object affect the copy. | `Object.assign({}, obj)` or `spread operator (...)` |
| **Deep Copy** | Creates an entirely new object, copying all nested structures. Changes in the original do not affect the copy. | `JSON.parse(JSON.stringify(obj))` or using **Lodash** (`_.cloneDeep(obj)`) |

---

## 🎯 Example of Shallow Copy
```js
let obj1 = { name: "Sameer", details: { age: 25 } };
let obj2 = { ...obj1 }; // Shallow Copy
obj2.details.age = 30;
console.log(obj1.details.age); // 30 (Original object also changes)
```

### ❌ Problem: Changes affect both copies.

---

## 🎯 Example of Deep Copy
```js
let obj1 = { name: "Sameer", details: { age: 25 } };
let obj2 = JSON.parse(JSON.stringify(obj1)); // Deep Copy
obj2.details.age = 30;
console.log(obj1.details.age); // 25 (Original object remains unchanged)
```

### ✅ Solution: Deep Copy creates a truly independent copy.

---

## 🚀 Best Practices
✔️ Use **shallow copy** (`spread operator` or `Object.assign`) when nested structures are **not modified**.
✔️ Use **deep copy** (`JSON.parse(JSON.stringify(obj)`) for **complex objects**.
✔️ For better performance, use **Lodash** (`_.cloneDeep(obj)`) for deep copying large objects.

---

This helps avoid **unexpected mutations** in your JavaScript applications! 🚀

