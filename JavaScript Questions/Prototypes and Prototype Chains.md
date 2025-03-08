# Prototypes and Prototype Chains in JavaScript

## 1️⃣ What is a Prototype?
In JavaScript, **every object** has a built-in property called `prototype`, which allows objects to inherit properties and methods from other objects.

### Example:
```js
function Person(name) {
  this.name = name;
}
Person.prototype.greet = function() {
  console.log("Hello, " + this.name);
};

const user = new Person("Sameer");
user.greet(); // "Hello, Sameer"
```
Here, `greet` is defined on `Person.prototype`, so all instances of `Person` inherit this method.

---

## 2️⃣ What is the Prototype Chain?
- If a property or method is **not found** on an object, JavaScript looks up the prototype chain to find it.
- This chain continues until it reaches `Object.prototype`, which is the top of the chain.

### Example:
```js
console.log(user.toString());
```
- `toString()` is not defined in `user` or `Person.prototype`, so JavaScript finds it in `Object.prototype`.

---

## 3️⃣ Understanding the Chain:
```js
console.log(user.__proto__ === Person.prototype); // true
console.log(Person.prototype.__proto__ === Object.prototype); // true
console.log(Object.prototype.__proto__); // null (end of chain)
```

---

## 🔥 Summary:
| Concept | Explanation |
|---------|-------------|
| **Prototype** | Object from which another object inherits properties/methods. |
| **Prototype Chain** | The lookup mechanism when accessing a property not directly found in an object. |
| **Object.prototype** | The topmost prototype from which all objects inherit. |

🚀 Prototypes allow **inheritance** and make JavaScript objects more efficient!

