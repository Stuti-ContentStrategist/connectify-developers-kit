# 🧯 Troubleshooting

Even with the best setup, you may encounter errors or unexpected behaviors while using the **Connectify JavaScript SDK**.

This section helps you identify and resolve common issues quickly.

***

#### ⚠️ Common Errors

**1. Missing or Invalid API Key**

**Cause:** The SDK cannot authenticate your requests.\
**Fix:**

* Verify that your API key is correctly set in the configuration.
* Ensure that the key has not expired or been revoked.

```javascript
javascript

const client = new ConnectifySDK({
  apiKey: process.env.CONNECTIFY_API_KEY
});
```

***

**2. Connection Timeout**

**Cause:** Network latency or incorrect endpoint configuration.\
**Fix:**

* Check your internet connection.
* Confirm the API base URL in your configuration.
* Retry with exponential backoff.

***

**3. Unhandled Promise Rejection**

**Cause:** Missing `catch()` block in async operations.\
**Fix:** Always handle rejections gracefully.

```javascript
javascript

client.devices.list()
  .then(devices => console.log(devices))
  .catch(err => console.error("Error fetching devices:", err));
```

***

#### 🧩 Debugging Tips

*   Enable debug mode by setting:

    ```bash
    export CONNECTIFY_DEBUG=true
    ```

    This logs detailed request and response information to help diagnose issues.
* For browser environments, check the **Console tab** for SDK logs.
* For Node.js, inspect your **terminal output** or **log files**.

***

#### 💡 Tip

If an issue persists, you can submit a support ticket with your debug logs and SDK version details.\
This helps our team replicate and resolve your problem faster.

***

#### 📚 Next Step

👉 [📘 **API Reference**](broken-reference)
