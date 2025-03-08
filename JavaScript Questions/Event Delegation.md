# Event Delegation in JavaScript

## 🔥 What is Event Delegation?
**Event Delegation** is a JavaScript technique where a **parent element** handles events for its **child elements**, even if they are added dynamically. It helps in improving performance and managing events efficiently.

---

## ✅ How It Works:
- Instead of adding event listeners to multiple child elements, **attach a single event listener to the parent**.
- The event **bubbles up** from the target element to its ancestors.
- Use **`event.target`** to identify which child element triggered the event.

---

## 🎯 Example: Without Event Delegation
```js
// Adding event listeners to each button separately
const buttons = document.querySelectorAll(".btn");
buttons.forEach(button => {
    button.addEventListener("click", () => {
        console.log("Button clicked!");
    });
});
```
### ❌ Problem:
- Inefficient when handling many elements.
- Cannot handle dynamically added elements.

---

## 🎯 Example: With Event Delegation
```js
// Adding a single event listener to the parent element
const parent = document.querySelector("#parent");
parent.addEventListener("click", (event) => {
    if (event.target.classList.contains("btn")) {
        console.log("Button clicked!");
    }
});
```
### ✅ Benefits:
✔️ **Better Performance** – One listener instead of many.
✔️ **Handles Dynamic Elements** – Works even for newly added buttons.
✔️ **Cleaner Code** – Reduces redundancy.

---

## 🚀 Best Practices
✔️ Use **event delegation** for lists, tables, or dynamically generated elements.
✔️ Always check **`event.target`** before executing logic.
✔️ Use **`stopPropagation()`** carefully to prevent unwanted bubbling effects.

