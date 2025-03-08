# useState & useEffect Hooks in React

## 🎯 useState Hook
- **Purpose:** Manages state in functional components.
- **Returns:** An array with two values:
  1. **State variable** (current state value)
  2. **Setter function** (to update state)

### 🔹 Example:
```jsx
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```
✅ Here, `useState(0)` initializes `count` as **0** and `setCount` updates it.

---

## 🎯 useEffect Hook
- **Purpose:** Handles **side effects** (e.g., API calls, event listeners, DOM updates).
- Runs **after render** and can be controlled using dependencies.

### 🔹 Example:
```jsx
import React, { useState, useEffect } from "react";

function Timer() {
  const [seconds, setSeconds] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => setSeconds((s) => s + 1), 1000);
    return () => clearInterval(interval); // Cleanup function
  }, []); // Empty dependency array → Runs once

  return <p>Timer: {seconds} sec</p>;
}
```
✅ Here, `useEffect` starts a timer **only once** (on mount) and clears it on unmount.

---

## 🔥 useEffect Dependency Variants
| Case | Syntax | Runs When? |
|------|--------|------------|
| **Run on every render** | `useEffect(fn);` | After every render |
| **Run only once (on mount)** | `useEffect(fn, []);` | On first render |
| **Run when state/props change** | `useEffect(fn, [state]);` | When `state` updates |
| **Cleanup function** | `return () => { cleanup }` | On unmount |

---

## 🎯 Summary
✅ **useState** → Manages state inside functional components.
✅ **useEffect** → Handles side effects (API calls, timers, subscriptions).
✅ **useEffect dependencies** allow controlling when effects run.

🚀 **Mastering these two hooks is crucial for React development!**