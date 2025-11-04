# 🔁 Async & Promises

The **Connectify JavaScript SDK** uses **Promises** and **async/await** syntax for handling asynchronous operations such as API requests, event triggers, and data updates.

This ensures smoother, non-blocking execution in both Node.js and browser environments.

***

#### ⚙️ Using Promises

Every SDK method returns a Promise that resolves with a response or rejects with an error.

```javascript
javascript

client.devices.getAll()
  .then((devices) => {
    console.log("Connected devices:", devices);
  })
  .catch((error) => {
    console.error("Error fetching devices:", error);
  });
```

***

#### 🧠 Using async/await

For cleaner syntax and better readability, you can use `async/await`:

<pre class="language-javascript"><code class="lang-javascript"><strong>javascript
</strong><strong>
</strong><strong>async function fetchDevices() {
</strong>  try {
    const devices = await client.devices.getAll();
    console.log("Devices:", devices);
  } catch (error) {
    console.error("Error:", error.message);
  }
}

fetchDevices();
</code></pre>

***

#### 🚀 Handling Multiple Requests

You can run multiple API calls concurrently using `Promise.all`:

```javascript
javascript

const [devices, events] = await Promise.all([
  client.devices.getAll(),
  client.events.getRecent(),
]);
```

***

#### 💡 Tip

Use `try...catch` blocks for async functions and `.catch()` for chained Promises to ensure consistent error handling throughout your application.

***

#### 📚 Next Step

👉 [🎯 **Event Handling**](event-handling.md)
