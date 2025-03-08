# Debouncing and Throttling in JavaScript

## 1️⃣ What is **Debouncing**?
Debouncing ensures that a function is executed **only after a certain delay** from the last time it was invoked. It is useful for optimizing frequent events like resizing, keypresses, and scrolling.

### ✅ Example:
```js
function debounce(func, delay) {
  let timer;
  return function (...args) {
    clearTimeout(timer);
    timer = setTimeout(() => func.apply(this, args), delay);
  };
}

function searchHandler() {
  console.log("Searching...");
}

const optimizedSearch = debounce(searchHandler, 500);
document.getElementById("search").addEventListener("input", optimizedSearch);
```
- The function runs **only after** 500ms of no input events.

---

## 2️⃣ What is **Throttling**?
Throttling ensures that a function **executes at most once** in a given time interval, no matter how many times the event is triggered.

### ✅ Example:
```js
function throttle(func, limit) {
  let lastCall = 0;
  return function (...args) {
    const now = Date.now();
    if (now - lastCall >= limit) {
      lastCall = now;
      func.apply(this, args);
    }
  };
}

function logScroll() {
  console.log("Scrolled!");
}

const optimizedScroll = throttle(logScroll, 1000);
window.addEventListener("scroll", optimizedScroll);
```
- The function runs **at most once per second** during continuous scrolling.

---

## 🔥 Summary:
| Concept     | Description |
|------------|-------------|
| **Debouncing** | Delays execution until inactivity for a set time. |
| **Throttling** | Limits execution to once per specified interval. |

🚀 **Use Debouncing** when you want to execute after a pause (e.g., search bar typing).
🚀 **Use Throttling** when you want periodic execution (e.g., handling scroll events).

