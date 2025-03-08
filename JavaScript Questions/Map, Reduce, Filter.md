# map(), filter(), and reduce() Methods in JavaScript

These are **higher-order functions** used for array manipulation in JavaScript.

## 1️⃣ `map()` – Transforms Each Element
- Creates a **new array** by applying a function to each element.

### Example:
```js
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(num => num * 2);
console.log(doubled); // [2, 4, 6, 8]
```

## 2️⃣ `filter()` – Filters Elements Based on a Condition
- Creates a **new array** with elements that pass a test.

### Example:
```js
const numbers = [1, 2, 3, 4, 5];
const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // [2, 4]
```

## 3️⃣ `reduce()` – Reduces an Array to a Single Value
- Uses an **accumulator** to process all elements.

### Example:
```js
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum); // 10
```

## 🔥 Summary
| Method  | Purpose | Returns |
|---------|---------|---------|
| `map()`  | Transforms elements | New array |
| `filter()` | Filters elements | New array |
| `reduce()` | Reduces to a single value | A value (e.g., sum) |

🚀 These methods make array manipulation easy and readable!

