## **Hoisting in JavaScript**

### **What is Hoisting?**
Hoisting is JavaScript's default behavior of moving **declarations** to the top of their scope before code execution.

- **Variables declared with `var` are hoisted but initialized as `undefined`.**
- **Variables declared with `let` and `const` are hoisted but not initialized (Temporal Dead Zone - TDZ).**
- **Function declarations are fully hoisted (can be called before they appear in code).**

---

### **Hoisting with `var`**
```js
console.log(a); // Output: undefined (Hoisted but not initialized)
var a = 10;
console.log(a); // Output: 10
```

#### **Behind the scenes:**
```js
var a;
console.log(a); // undefined
a = 10;
console.log(a); // 10
```

---

### **Hoisting with `let` and `const` (Temporal Dead Zone - TDZ)**
```js
// console.log(b); // ReferenceError: Cannot access 'b' before initialization
let b = 20;
console.log(b); // Output: 20
```
```js
// console.log(c); // ReferenceError: Cannot access 'c' before initialization
const c = 30;
console.log(c); // Output: 30
```

- `let` and `const` are hoisted but remain in **TDZ (Temporal Dead Zone)** until they are initialized.
- Accessing them before declaration results in **ReferenceError**.

---

### **Hoisting with Functions**
#### **Function Declaration (Hoisted)**
```js
sayHello(); // Output: Hello, World!

function sayHello() {
    console.log("Hello, World!");
}
```
- Function **declarations** are fully hoisted, meaning they can be called **before** being defined.

#### **Function Expression (Not Hoisted)**
```js
// greet(); // TypeError: greet is not a function

var greet = function() {
    console.log("Hello!");
};
```
- Function **expressions** are not hoisted the same way as function **declarations**.
- Since `greet` is declared with `var`, it is hoisted **without** its function definition.

---

## **Key Takeaways**
| Feature        | var | let | const | Function Declaration | Function Expression |
|---------------|-----|-----|-------|---------------------|---------------------|
| Hoisted       | ✅ Yes | ✅ Yes | ✅ Yes | ✅ Yes | ✅ Yes (Only variable) |
| Initialized?  | ❌ No (Undefined) | ❌ No (TDZ) | ❌ No (TDZ) | ✅ Yes | ❌ No |
| Usable Before Declaration? | ✅ Yes | ❌ No (TDZ Error) | ❌ No (TDZ Error) | ✅ Yes | ❌ No (TypeError) |

🚀 **Best Practice:** Always declare variables using `let` or `const` at the top of their scope to avoid unexpected behavior!

