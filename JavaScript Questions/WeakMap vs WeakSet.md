# WeakMap vs WeakSet in JavaScript

## 🔥 What are WeakMap and WeakSet?
- **WeakMap** and **WeakSet** are similar to **Map** and **Set**, but they only store **weakly referenced** objects.
- They **do not prevent garbage collection**, meaning if an object is no longer referenced anywhere else, it will be removed from memory automatically.

---

## 🎯 WeakMap
- Stores **key-value pairs** where keys **must** be objects.
- Keys are **weakly held**, meaning they can be garbage collected when no longer referenced.
- No iteration methods (like `forEach`) available.

### Example:
```js
let weakMap = new WeakMap();
let obj = { name: "Sameer" };
weakMap.set(obj, "Developer");
console.log(weakMap.get(obj)); // "Developer"
obj = null; // The object is removed from WeakMap automatically
```

### ✅ Use Cases:
✔ Storing **private data** related to DOM elements.
✔ Caching data without memory leaks.

---

## 🎯 WeakSet
- Stores **only objects**, not primitive values.
- Objects are **weakly held**, so they can be garbage collected.
- No iteration methods available (`forEach`, `values`, etc.).

### Example:
```js
let weakSet = new WeakSet();
let user = { name: "Sameer" };
weakSet.add(user);
console.log(weakSet.has(user)); // true
user = null; // The object is removed from WeakSet automatically
```

### ✅ Use Cases:
✔ Tracking objects without preventing garbage collection.
✔ Storing **temporary references** (like tracking active users).

---

## 🚀 Key Differences
| Feature     | WeakMap | WeakSet |
|------------|---------|---------|
| Stores     | Key-Value Pairs | Unique Objects |
| Keys/Values | Keys must be objects | Only objects (no primitives) |
| Iteration  | ❌ Not possible | ❌ Not possible |
| Garbage Collection | ✅ Yes | ✅ Yes |

---

## 🛠️ Best Practices
✔ Use **WeakMap** for caching and temporary data storage.
✔ Use **WeakSet** for tracking object states.
✔ Avoid using them when iteration is required.

🚀 **Memory-efficient collections for managing objects dynamically!**

