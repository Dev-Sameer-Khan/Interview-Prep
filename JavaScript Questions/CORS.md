# CORS (Cross-Origin Resource Sharing)

## 🔥 What is CORS?
CORS (Cross-Origin Resource Sharing) is a security feature implemented in web browsers that **controls how resources on a web page can be requested from another domain**.

By default, browsers block **cross-origin requests** due to the **Same-Origin Policy (SOP)** to prevent security risks.

---

## 📌 Why is CORS needed?
- Allows secure access to resources from different origins.
- Prevents malicious websites from accessing sensitive data from another site.
- Enables APIs to be consumed by web applications from different domains.

---

## ⚠️ Same-Origin Policy (SOP)
**Same-Origin Policy** restricts web pages from making AJAX requests to a different domain unless CORS is enabled.

**Same-Origin** means:
✅ `https://example.com/page1` → `https://example.com/page2` (Allowed)  
❌ `https://example.com` → `https://api.example.com` (Blocked unless CORS is enabled)

---

## 🚀 How to Enable CORS?
CORS is managed **on the server-side** by setting proper HTTP headers.

### ✅ Example: Allow CORS in Express.js (Node.js Server)
```js
const express = require('express');
const cors = require('cors');
const app = express();

app.use(cors()); // Enables CORS for all routes

app.get("/data", (req, res) => {
    res.json({ message: "CORS enabled!" });
});

app.listen(3000, () => console.log("Server running on port 3000"));
```

### ✅ Example: Allow Specific Origins
```js
app.use(cors({ origin: "https://example.com" }));
```

---

## 🔄 Summary
| Feature | Description |
|---------|-------------|
| **Same-Origin Policy** | Blocks requests from different domains for security. |
| **CORS** | Allows controlled access to resources from different origins. |
| **How to Enable?** | Set response headers (`Access-Control-Allow-Origin`). |

💡 **Use CORS when you need to share data between different domains securely!** 🚀

