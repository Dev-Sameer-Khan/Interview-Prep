# Optional Chaining (`?.`) in JavaScript

## 🔥 What is Optional Chaining?
Optional chaining (`?.`) is a **safe way to access nested object properties** without worrying about `undefined` or `null` errors.

---

## 🎯 Why Use Optional Chaining?
- Avoids `Cannot read property of undefined` errors.
- Reduces the need for multiple `if` checks.
- Makes code cleaner and more readable.

---

## 📌 Example Without Optional Chaining
```js
let user = { profile: { name: "Sameer" } };
console.log(user.profile.name); // "Sameer"
console.log(user.address.city); // ❌ Error: Cannot read property 'city' of undefined
```

### ✅ Fix Using Optional Chaining
```js
console.log(user?.profile?.name); // "Sameer"
console.log(user?.address?.city); // ✅ No error, returns 'undefined'
```

---

## 🚀 Where Can You Use `?.`?
1️⃣ **Accessing Object Properties:**
```js
let data = { user: { name: "Sameer" } };
console.log(data?.user?.name); // "Sameer"
console.log(data?.account?.balance); // undefined (no error)
```

2️⃣ **Calling Functions Safely:**
```js
let obj = { greet: () => "Hello!" };
console.log(obj.greet?.()); // "Hello!"
console.log(obj.sayBye?.()); // undefined (no error)
```

3️⃣ **Accessing Array Elements:**
```js
let arr = [ { name: "Sameer" }, { name: "Ali" } ];
console.log(arr[1]?.name); // "Ali"
console.log(arr[5]?.name); // undefined (no error)
```

---

## 🔄 Benefits of Optional Chaining
✔ Prevents unnecessary crashes.
✔ Simplifies complex conditional checks.
✔ Works with objects, arrays, and functions.

🚀 **Use `?.` to make your JavaScript code more robust and error-free!**

