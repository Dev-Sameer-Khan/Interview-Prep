# Garbage Collection in JavaScript

## 🔥 What is Garbage Collection?
Garbage collection (GC) is the process in JavaScript that automatically **frees up memory** by removing objects that are no longer accessible.

---

## 🛠 How Does It Work?
JavaScript uses **automatic garbage collection** based on **Reachability**.
- If an object is **reachable**, it is kept in memory.
- If an object is **unreachable**, it is removed from memory.

### ✅ Example:
```js
let obj = { name: "John" }; // Object created in memory
obj = null; // Now, it's unreachable and will be garbage collected
```

---

## ♻️ Garbage Collection Mechanisms
### 1️⃣ **Reference Counting** (Old Method)
- Keeps track of the number of references to an object.
- If the reference count drops to `0`, the object is collected.
- Issue: Circular references cause memory leaks.

### 🔥 Example of a Memory Leak:
```js
let a = {};
let b = {};
a.ref = b;
b.ref = a; // Circular reference, won't be garbage collected
```

### 2️⃣ **Mark-and-Sweep Algorithm** (Modern Method)
- The **JS engine** starts from **root objects** (e.g., `window`, `document`).
- Marks all reachable objects.
- Sweeps and removes unreachable objects.

---

## 🏆 Best Practices to Avoid Memory Leaks
✅ **Nullify references when no longer needed:**
```js
let data = { key: "value" };
data = null; // Now eligible for garbage collection
```
✅ **Use WeakMap & WeakSet** (They don’t prevent garbage collection):
```js
let weakMap = new WeakMap();
let obj = {};
weakMap.set(obj, "value");
obj = null; // Removed from memory
```
✅ **Avoid global variables** (They stay in memory till the page unloads).

🚀 **JavaScript automatically handles memory, but good coding practices help optimize performance!**

