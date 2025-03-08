# Event Bubbling vs Event Capturing

## **Event Bubbling (Bottom to Top)**
- The event starts from the target element and moves **up** to the root.
- Default behavior in JavaScript.
- Handlers on parent elements are triggered **after** child elements.

```js
// Example of Event Bubbling
document.getElementById("child").addEventListener("click", () => {
    console.log("Child Clicked");
});
document.getElementById("parent").addEventListener("click", () => {
    console.log("Parent Clicked");
});
// Clicking on the child will log:
// "Child Clicked"
// "Parent Clicked" (Bubbles up)
```

## **Event Capturing (Top to Bottom)**
- The event starts from the **root** and moves **down** to the target element.
- Activated by passing `true` as the third argument in `addEventListener`.

```js
// Example of Event Capturing
document.getElementById("child").addEventListener("click", () => {
    console.log("Child Clicked");
}, true);
document.getElementById("parent").addEventListener("click", () => {
    console.log("Parent Clicked");
}, true);
// Clicking on the child will log:
// "Parent Clicked" (Captures first)
// "Child Clicked"
```