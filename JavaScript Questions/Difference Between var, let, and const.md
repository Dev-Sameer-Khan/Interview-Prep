## **Difference Between var, let, and const**

### **1. var** (Function Scoped, Hoisted)
- Can be **redeclared** and **updated**.
- **Function-scoped** (Not blocked by `{}` except in functions).
- **Hoisted** (Can be accessed before declaration, but will be `undefined`).

#### **Example:**
```js
console.log(a); // Undefined (hoisted but not initialized)
var a = 10;
console.log(a); // 10

var a = 20; // Redeclaration allowed
console.log(a); // 20
```

---

### **2. let** (Block Scoped, No Hoisting)
- Can be **updated** but **cannot be redeclared** in the same scope.
- **Block-scoped** (Limited to `{}` where it is declared).
- **Not hoisted** (Cannot be accessed before declaration).

#### **Example:**
```js
// console.log(b); // Error: Cannot access 'b' before initialization
let b = 15;
console.log(b); // 15

b = 25; // Allowed
console.log(b); // 25

// let b = 30; // Error: Identifier 'b' has already been declared
```

---

### **3. const** (Block Scoped, Immutable)
- **Cannot be updated or redeclared**.
- **Block-scoped** (Same as `let`).
- **Must be initialized** during declaration.

#### **Example:**
```js
const c = 50;
console.log(c); // 50

// c = 60; // Error: Assignment to constant variable
// const c = 70; // Error: Identifier 'c' has already been declared
```

---

## **Key Differences**

| Feature   | var | let | const |
|-----------|-----|-----|-------|
| Scope | Function-scoped | Block-scoped | Block-scoped |
| Redeclaration | ✅ Allowed | ❌ Not Allowed | ❌ Not Allowed |
| Reassignment | ✅ Allowed | ✅ Allowed | ❌ Not Allowed |
| Hoisting | ✅ Hoisted (initialized as `undefined`) | ❌ No Hoisting | ❌ No Hoisting |
| Must Initialize | ❌ No | ❌ No | ✅ Yes |

🚀 Use `let` for variables that change and `const` for constants to write **better and safer JavaScript code**!