# Difference Between `useRef` and `createRef` in React

## 🎯 Overview
Both `useRef` and `createRef` are used to create references to DOM elements or persist values across renders in React, but they have key differences in usage and behavior.

---

## 🔹 `useRef` (Used in Functional Components)
- **Persistent:** Maintains the same reference **across re-renders**.
- **Does NOT trigger re-renders** when updated.
- **Used for:**
  - Accessing/manipulating DOM elements.
  - Storing mutable values without causing re-renders.

### ✅ Example:
```jsx
import React, { useRef } from "react";

function InputFocus() {
  const inputRef = useRef(null);

  const handleFocus = () => {
    inputRef.current.focus();
  };

  return (
    <div>
      <input ref={inputRef} type="text" placeholder="Type here..." />
      <button onClick={handleFocus}>Focus Input</button>
    </div>
  );
}

export default InputFocus;
```
✅ The reference **remains the same** across renders.

---

## 🔹 `createRef` (Used in Class Components)
- **Not Persistent:** Creates a **new reference** on every render.
- **Used mostly in class components.**

### ✅ Example:
```jsx
import React, { Component, createRef } from "react";

class InputFocus extends Component {
  constructor(props) {
    super(props);
    this.inputRef = createRef();
  }

  handleFocus = () => {
    this.inputRef.current.focus();
  };

  render() {
    return (
      <div>
        <input ref={this.inputRef} type="text" placeholder="Type here..." />
        <button onClick={this.handleFocus}>Focus Input</button>
      </div>
    );
  }
}

export default InputFocus;
```
✅ The reference **resets on each render**.

---

## 🎯 Key Differences
| Feature         | `useRef` (Functional) | `createRef` (Class) |
|---------------|--------------------|----------------|
| **Re-renders?** | ❌ No | ✅ Yes |
| **Persists Across Renders?** | ✅ Yes | ❌ No |
| **Use Case** | DOM access, storing values | DOM access in class components |

---

## 🚀 Best Practices
- Use **`useRef`** for **functional components** (better for performance).
- Use **`createRef`** only in **class components** (not needed in modern React).
- Prefer **state over refs** when values should trigger re-renders.

✅ **Conclusion:** `useRef` is widely preferred in modern React development! 🚀

