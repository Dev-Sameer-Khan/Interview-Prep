# Difference Between `==` and `===`

## `==` (Loose Equality)
- Compares **values only**, not types.
- Converts values to the same type before comparing.

### Example:
```js
console.log(5 == "5");  // true (string converted to number)
console.log(true == 1);  // true (true converted to 1)
console.log(null == undefined); // true
```

## `===` (Strict Equality)
- Compares **both values and types**.
- No type conversion happens.

### Example:
```js
console.log(5 === "5");  // false (different types)
console.log(true === 1);  // false (boolean vs number)
console.log(null === undefined); // false
```

### Best Practice:
- Use `===` for accurate comparisons and to avoid unexpected results.