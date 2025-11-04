# ⚠️ Error Handling

The **Connectify Software Development Kit (SDK)** provides a structured and consistent error-handling mechanism that helps you identify, debug, and resolve issues efficiently.

Every SDK method and API call returns well-defined exceptions or error codes, making it easier to manage unexpected behaviors gracefully.

#### 🧱 Error Types

1. **Client Errors (4xx)**\
   Occur when a request is invalid or unauthorized.\
   Examples:
   * `400 Bad Request` — Incorrect parameters or missing fields
   * `401 Unauthorized` — Invalid or expired authentication token
   * `404 Not Found` — The requested resource doesn’t exist
2. **Server Errors (5xx)**\
   Indicate issues on the Connectify server side.\
   Examples:
   * `500 Internal Server Error` — Unexpected system failure
   * `503 Service Unavailable` — Temporary downtime or overload
3. **SDK Exceptions**\
   Custom exceptions raised by the SDK itself for local or logic-related issues.\
   Examples:
   * `ConfigurationError` — Invalid environment setup
   * `ConnectionError` — Network-related failure
   * `TimeoutError` — API request exceeded response time

#### 🧩 Example (Python)

```python
python

from connectify_sdk import ConnectifyClient, ConnectifyError

try:
    client = ConnectifyClient(api_key="your_api_key")
    device = client.get_device("device_id")
except ConnectifyError as e:
    print(f"Error: {e.message}")
```

This pattern ensures that every potential issue — whether in communication, configuration, or server response — is caught and handled cleanly.

#### 💡 Best Practices

* **Always wrap API calls in** `try-except` (or equivalent) blocks.
* **Log detailed error messages** for debugging.
* **Avoid exposing sensitive data** (like tokens) in logs.
* **Use retry logic** for transient network or server errors.

***

#### 📚 **Next Page**

👉 [🐍 Python SDK](broken-reference)
