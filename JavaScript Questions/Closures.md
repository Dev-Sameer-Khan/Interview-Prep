# What are Closures in JavaScript?

A **closure** is a function that **remembers** the variables from its **outer scope**, even after the outer function has finished execution.

## Why Use Closures?
- **Encapsulation:** Helps create private variables.
- **State Maintenance:** Useful in event listeners, timers, and callbacks.

## Example 1: Basic Closure
```js
function outerFunction() {
    let count = 0; // Local variable
    
    return function innerFunction() {
        count++;
        console.log("Count:", count);
    };
}

const counter = outerFunction();
counter(); // Count: 1
counter(); // Count: 2
```
🔹 `innerFunction` remembers `count` even after `outerFunction` has executed.

## Example 2: Closures in `setTimeout`
```js
function delayedMessage(msg, delay) {
    setTimeout(function() {
        console.log(msg);
    }, delay);
}

delayedMessage("Hello after 2 seconds!", 2000);
```
🔹 The inner function remembers `msg` and `delay` even after `delayedMessage` execution.

## Best Practice:
- Avoid memory leaks by not creating unnecessary closures.
- Use closures for maintaining **state** and **data privacy**.

🚀 Closures are a powerful concept in JavaScript for handling functions and scope effectively!