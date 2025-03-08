# Prop Drilling in React

## 🎯 What is Prop Drilling?
- **Definition:** Prop drilling occurs when **props** are passed down through multiple levels of components **just to be used by a deeply nested child component**.
- **Issue:** It makes the code **hard to maintain** and **clutters** intermediate components.

---

## 🔹 Example of Prop Drilling
```jsx
import React from "react";

function Grandparent() {
  const message = "Hello from Grandparent!";
  return <Parent message={message} />;
}

function Parent({ message }) {
  return <Child message={message} />;
}

function Child({ message }) {
  return <p>{message}</p>;
}

export default Grandparent;
```
✅ Here, `message` is **prop drilled** through `Parent` to reach `Child`.

---

## 🛠️ How to Avoid Prop Drilling?
### 1️⃣ **Using Context API**
```jsx
import React, { createContext, useContext } from "react";

const MessageContext = createContext();

function Grandparent() {
  return (
    <MessageContext.Provider value="Hello from Context!">
      <Parent />
    </MessageContext.Provider>
  );
}

function Parent() {
  return <Child />;
}

function Child() {
  const message = useContext(MessageContext);
  return <p>{message}</p>;
}

export default Grandparent;
```
✅ **Context API** eliminates the need for prop drilling by **providing values globally**.

### 2️⃣ **Using State Management (Redux, Zustand, Recoil)**
- When multiple components need the same data, **state management libraries** like Redux or Zustand help store and manage the state centrally.

---

## 🎯 Summary
✅ **Prop Drilling** happens when props are unnecessarily passed down multiple levels.
✅ It makes components **harder to manage** and **less reusable**.
✅ **Solutions:** Use **Context API** or **State Management Libraries** (like Redux, Zustand).

🚀 **Avoiding prop drilling keeps React code clean and maintainable!**

