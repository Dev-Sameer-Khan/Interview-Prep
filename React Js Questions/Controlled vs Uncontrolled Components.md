# Controlled vs Uncontrolled Components in React

## 🎛 Controlled Components
- **React controls the form elements** (input, textarea, etc.).
- The component's state holds the **value** and updates it via `setState` or `useState`.
- The UI **re-renders** whenever the value changes.

### 🔹 Example:
```jsx
import React, { useState } from "react";

function ControlledInput() {
  const [text, setText] = useState("");

  return (
    <input type="text" value={text} onChange={(e) => setText(e.target.value)} />
  );
}
```
✅ **Here:** `value={text}` is controlled by `useState`, making it a **controlled component**.

---

## 🎛 Uncontrolled Components
- **The DOM controls the form elements**, not React.
- Uses `useRef` to access values instead of state.
- No re-render happens when value changes.

### 🔹 Example:
```jsx
import React, { useRef } from "react";

function UncontrolledInput() {
  const inputRef = useRef(null);

  const handleSubmit = () => {
    alert(inputRef.current.value);
  };

  return (
    <>
      <input type="text" ref={inputRef} />
      <button onClick={handleSubmit}>Submit</button>
    </>
  );
}
```
✅ **Here:** The input is not controlled by state; instead, `useRef` is used, making it **uncontrolled**.

---

## 🔥 Key Differences
| Feature  | Controlled Component  | Uncontrolled Component  |
|----------|----------------------|------------------------|
| **Control** | React controls input value | Browser (DOM) controls input |
| **State** | Uses `useState` | Uses `useRef` |
| **Re-renders** | On every change | Does not re-render |
| **Best For** | Form validation, dynamic inputs | Simpler forms, direct DOM access |

---

## 🎯 Summary
✅ **Controlled Components** are React-driven and ideal for handling dynamic inputs & validation.
✅ **Uncontrolled Components** rely on the DOM, making them simpler but less flexible.
✅ Use **controlled components** for better React state management!

🚀 **Understanding both helps in choosing the right approach for forms in React!**

