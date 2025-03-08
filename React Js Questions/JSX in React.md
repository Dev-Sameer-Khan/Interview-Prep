# What is JSX in React?

## 🚀 What is JSX?
JSX (**JavaScript XML**) is a **syntax extension** for JavaScript used in React to write **HTML-like code** inside JavaScript.

### ✅ Key Features:
- **Looks Like HTML** – Easier to write UI inside JavaScript.
- **JSX is Not HTML** – It gets converted to JavaScript.
- **Babel Transpilation** – JSX is compiled into `React.createElement()` calls.
- **Can Embed JavaScript Expressions** using `{}`.

---

## 🔥 Why Use JSX?
JSX makes **React development faster and more readable**.

### 📌 Benefits:
1️⃣ **Easier to Read & Write** – Looks like HTML inside JavaScript.
2️⃣ **Better Performance** – Optimized by React’s Virtual DOM.
3️⃣ **Prevents XSS Attacks** – JSX escapes expressions by default.
4️⃣ **Powerful UI Composition** – Helps in writing complex UIs more cleanly.

---

## 📝 Example:
### ✅ Using JSX:
```jsx
import React from "react";

function App() {
  const name = "Sameer";
  return <h1>Hello, {name}! 🚀</h1>;
}

export default App;
```

### ❌ Without JSX (Using `React.createElement`):
```js
import React from "react";

function App() {
  return React.createElement("h1", null, "Hello, React! 🚀");
}

export default App;
```

---

### 📌 Summary:
✅ JSX makes React **simpler, cleaner, and more intuitive**.
✅ It is **not required**, but **highly recommended** for better readability.
✅ It gets compiled to JavaScript and **improves performance**.

🚀 **JSX = HTML-like Syntax + JavaScript Power!**