# Difference Between State and Props in React

## 🛠 What is **State**?
- **State** is an object that holds dynamic data and determines how a component behaves.
- It is **mutable** (can be changed using `setState` or `useState`).
- Used **within a component** to track changes.

### 🔹 Example:
```jsx
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h1>{count}</h1>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```
✅ **Here:** `count` is **state**, and `setCount` updates it dynamically.

---

## 🎁 What are **Props**?
- **Props (short for properties)** are used to pass data from a **parent** to a **child** component.
- They are **immutable** (cannot be changed inside the child component).
- Help in **component reusability** and **data flow**.

### 🔹 Example:
```jsx
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

function App() {
  return <Greeting name="Sameer" />;
}
```
✅ **Here:** `name="Sameer"` is passed as a **prop** to the `Greeting` component.

---

## 🔥 Key Differences
| Feature  | State  | Props  |
|----------|--------|--------|
| **Definition** | Internal data storage | External data passed to components |
| **Mutability** | Mutable (can change) | Immutable (cannot change) |
| **Scope** | Local to the component | Passed from parent to child |
| **Usage** | Managing component behavior | Reusing and passing data |

---

## 🎯 Summary
✅ **State** is used for managing **internal data** and changes within a component.
✅ **Props** are used for passing **read-only data** from one component to another.
✅ Use **State** when data needs to change, and **Props** when data should remain constant.

🚀 **Both are essential for building dynamic and interactive React applications!**

