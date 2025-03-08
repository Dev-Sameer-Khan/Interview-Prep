# Call, Apply, and Bind Methods in JavaScript

## 🔥 What are `call()`, `apply()`, and `bind()`?
These methods are used to **change the `this` context** of a function and invoke it with a specified object.

---

## 📌 `call()` Method
- Calls a function **immediately** with a given `this` value and arguments passed **individually**.

### ✅ Example:
```js
function greet(language) {
    console.log(`${language}: Hello, my name is ${this.name}`);
}

const user = { name: "Sameer" };

greet.call(user, "English"); // English: Hello, my name is Sameer
```

---

## 📌 `apply()` Method
- Similar to `call()`, but arguments are passed **as an array**.

### ✅ Example:
```js
greet.apply(user, ["French"]); // French: Hello, my name is Sameer
```

---

## 📌 `bind()` Method
- **Returns a new function** with `this` bound to the specified object, without calling it immediately.

### ✅ Example:
```js
const boundGreet = greet.bind(user, "Spanish");
boundGreet(); // Spanish: Hello, my name is Sameer
```

---

## 🔄 Summary
| Method  | Calls Immediately? | Arguments Format |
|---------|------------------|-----------------|
| `call`  | ✅ Yes           | Individual values |
| `apply` | ✅ Yes           | Array           |
| `bind`  | ❌ No (returns function) | Individual values |

🚀 **Use `call()` and `apply()` for immediate invocation, and `bind()` when you need a function with a fixed `this`!**

