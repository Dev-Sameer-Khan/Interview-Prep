# Difference Between localStorage and sessionStorage

Both `localStorage` and `sessionStorage` are part of the **Web Storage API** used to store key-value pairs in the browser.

## 1️⃣ `localStorage`
- **Data persists** even after the browser is closed.
- Stores data with **no expiration time**.
- Accessible from the same origin (protocol + domain + port).

### Example:
```js
localStorage.setItem("name", "Sameer");
console.log(localStorage.getItem("name")); // "Sameer"
localStorage.removeItem("name");
```

## 2️⃣ `sessionStorage`
- Data is stored **only for the session**.
- **Clears** when the browser is closed.
- Accessible only within the same tab.

### Example:
```js
sessionStorage.setItem("role", "Developer");
console.log(sessionStorage.getItem("role")); // "Developer"
sessionStorage.removeItem("role");
```

## 🔥 Summary
| Feature | localStorage | sessionStorage |
|---------|-------------|---------------|
| **Persistence** | Permanent (until cleared) | Only for session |
| **Scope** | Across all tabs/windows | Only in the same tab |
| **Cleared on Browser Close?** | ❌ No | ✅ Yes |

🚀 Use `localStorage` for long-term storage & `sessionStorage` for temporary data!