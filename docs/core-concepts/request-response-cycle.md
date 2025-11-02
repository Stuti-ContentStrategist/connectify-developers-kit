# 🔄 Request–Response Cycle

The **Request–Response Cycle** defines how your application communicates with the Connectify Platform through the **Connectify Developer’s Kit (CDK)**.\
Understanding this flow helps you design reliable API calls, handle responses correctly, and manage errors efficiently.

#### ⚙️ How It Works

1. **Request Creation**\
   The SDK builds a structured request containing:
   * The API endpoint
   * HTTP method (GET, POST, PUT, DELETE)
   * Authentication token
   * Request body or parameters
2. **Request Transmission**\
   The SDK sends the request to Connectify’s API Gateway using secure HTTPS protocols.
3. **Processing on Server**\
   The Connectify server validates the authentication token, processes your request, and interacts with relevant internal services (devices, automations, or integrations).
4. **Response Handling**\
   The server sends back a JSON response, which the SDK interprets and converts into a data model for easier access in your code.
5. **Error Management**\
   If the server returns an error, the SDK provides a structured exception or error message that can be logged, retried, or displayed to the user.

#### 📊 Example Flow

```arduino
arduino

Client App  →  SDK  →  Connectify API  →  Response  →  SDK  →  Client App
```

#### 💡 Best Practices

* Always handle both **success** and **error** responses.
* Log request and response details for debugging during development.
* Avoid blocking calls; use asynchronous methods wherever possible.

💡 **Tip:** Use the SDK’s built-in logging and retry mechanisms to ensure smooth and reliable communication with Connectify’s servers.

***

#### 📚 **Next Steps**

👉 [Data Models](data-models.md)\
👉 [Error Handling](error-handling.md)
