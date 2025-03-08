# Difference Between `setTimeout` and `setInterval`

## `setTimeout()`
- Executes a function **once** after a specified delay.
- Used for delayed execution.

### ✅ Example:
```js
setTimeout(() => {
  console.log("Hello after 2 seconds");
}, 2000);
```
**Output:** Logs "Hello after 2 seconds" once.

---

## `setInterval()`
- Executes a function **repeatedly** at a specified time interval.
- Used for periodic tasks like updating UI, animations, or clocks.

### ✅ Example:
```js
setInterval(() => {
  console.log("Hello every 2 seconds");
}, 2000);
```
**Output:** Logs "Hello every 2 seconds" repeatedly.

---

## 🔥 Key Differences:
| Feature           | `setTimeout` | `setInterval` |
|------------------|-------------|--------------|
| Execution       | Runs **once** | Runs **repeatedly** |
| Use Case        | Delay a function execution | Repeat a function execution |
| Clear Method    | `clearTimeout(timeoutID)` | `clearInterval(intervalID)` |

### ✅ Stopping Execution:
```js
let timer = setTimeout(() => console.log("This won't run"), 2000);
clearTimeout(timer);

let interval = setInterval(() => console.log("This won't repeat"), 2000);
clearInterval(interval);
```
🚀 Use `clearTimeout()` to stop `setTimeout()` and `clearInterval()` to stop `setInterval()`.

