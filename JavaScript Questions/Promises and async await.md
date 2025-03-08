# Promises and async/await in JavaScript

## 1️⃣ Promises – Handling Asynchronous Code
A **Promise** represents a value that may be available **now, later, or never**. It helps in managing asynchronous operations.

### States of a Promise:
- **Pending**: Initial state
- **Resolved (Fulfilled)**: Operation completed successfully
- **Rejected**: Operation failed

### Example:
```js
const fetchData = new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve("Data fetched successfully!");
    }, 2000);
});

fetchData.then(response => console.log(response))
         .catch(error => console.log(error));
```

## 2️⃣ async/await – Simplifying Promises
- `async` makes a function return a **Promise**.
- `await` waits for a Promise to resolve **before moving forward**.

### Example:
```js
async function getData() {
    try {
        let response = await fetchData;
        console.log(response);
    } catch (error) {
        console.log(error);
    }
}

gData();
```

## 🔥 Summary
| Feature | Purpose |
|---------|---------|
| **Promises** | Handles asynchronous operations using `.then()` & `.catch()` |
| **async/await** | Makes asynchronous code look synchronous |

🚀 Use `async/await` for **cleaner**, more readable code!

