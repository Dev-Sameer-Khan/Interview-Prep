# What is a Callback Function?

A **callback function** is a function that is **passed as an argument** to another function and is **executed later**, after the completion of an operation.

## Why Use Callbacks?
- Helps in **asynchronous programming** (e.g., handling API requests, setTimeout, event listeners).
- Allows functions to be **executed in sequence**.

## Example 1: Basic Callback
```js
function greet(name, callback) {
    console.log("Hello, " + name);
    callback(); // Execute the callback function
}

function sayBye() {
    console.log("Goodbye!");
}

greet("Sameer", sayBye);
```
**Output:**
```
Hello, Sameer
Goodbye!
```

## Example 2: Using Callbacks in `setTimeout`
```js
setTimeout(function() {
    console.log("This runs after 2 seconds");
}, 2000);
```

## Example 3: Callback in Array Methods
```js
const numbers = [1, 2, 3, 4];

numbers.forEach(function(num) {
    console.log(num * 2); // Doubles each number
});
```

## Best Practice:
- Always **name** callback functions for better readability.
- Handle **errors** properly in asynchronous operations.

🚀 Callbacks are widely used in JavaScript for handling asynchronous tasks efficiently!

