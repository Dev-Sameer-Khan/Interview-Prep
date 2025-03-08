# Handling API Calls in React

## Using Fetch API
Fetch API is a built-in JavaScript method to make HTTP requests.

### Example:
```js
import { useEffect, useState } from "react";

function FetchData() {
    const [data, setData] = useState(null);
    
    useEffect(() => {
        fetch("https://api.example.com/data")
            .then(response => response.json())
            .then(result => setData(result))
            .catch(error => console.error("Error fetching data:", error));
    }, []);
    
    return <div>{data ? JSON.stringify(data) : "Loading..."}</div>;
}

export default FetchData;
```

---

## Using Axios
Axios is a promise-based HTTP client that simplifies API requests.

### Install Axios:
```sh
npm install axios
```

### Example:
```js
import { useEffect, useState } from "react";
import axios from "axios";

function FetchData() {
    const [data, setData] = useState(null);
    
    useEffect(() => {
        axios.get("https://api.example.com/data")
            .then(response => setData(response.data))
            .catch(error => console.error("Error fetching data:", error));
    }, []);
    
    return <div>{data ? JSON.stringify(data) : "Loading..."}</div>;
}

export default FetchData;
```

---

## Best Practices
1. **Use `useEffect` to Fetch Data on Component Mount** ✅
2. **Use State to Store API Response** ✅
3. **Handle Errors Gracefully** ✅
4. **Use `axios` for Simplicity and Better Error Handling** ✅
5. **Use `async/await` for Better Readability** ✅

