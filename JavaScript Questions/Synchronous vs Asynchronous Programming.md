## **Synchronous vs Asynchronous Programming**

### **Synchronous Programming (Blocking)**
- Executes code line by line in order.
- One task must complete before the next one starts.
- Can cause performance issues if a task takes too long.

#### **Example:**
```js
console.log("Step 1");
console.log("Step 2");
console.log("Step 3");
// Output: Step 1, Step 2, Step 3 (in order)
```

---

### **Asynchronous Programming (Non-blocking)**
- Code does not wait for a task to finish before moving to the next one.
- Improves performance by handling multiple tasks at once.
- Uses callbacks, promises, and async/await.

#### **Example:**
```js
console.log("Step 1");
setTimeout(() => console.log("Step 2"), 2000); // Executes after 2 seconds
console.log("Step 3");
// Output: Step 1, Step 3, Step 2 (Step 2 runs later)
```

---

## **Key Differences**
| Synchronous | Asynchronous |
|------------|-------------|
| Executes tasks sequentially | Can execute multiple tasks simultaneously |
| Blocks execution until a task is completed | Does not block execution; continues running other tasks |
| Slower performance if a task takes too long | Faster and more efficient |

---

## **How to Handle Asynchronous Code?**

### **1. Callbacks**
- A function passed as an argument to another function, executed later.
```js
function fetchData(callback) {
    setTimeout(() => {
        console.log("Data fetched");
        callback();
    }, 2000);
}
fetchData(() => console.log("Callback executed"));
```

### **2. Promises**
- Handles asynchronous operations and avoids callback hell.
```js
let myPromise = new Promise((resolve, reject) => {
    setTimeout(() => resolve("Promise resolved"), 2000);
});
myPromise.then(data => console.log(data));
```

### **3. Async/Await**
- Simplifies promise-based code.
```js
async function fetchData() {
    let data = await new Promise(resolve => setTimeout(() => resolve("Async Data"), 2000));
    console.log(data);
}
fetchData();
```