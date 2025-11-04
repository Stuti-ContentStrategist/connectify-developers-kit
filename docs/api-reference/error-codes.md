# ❌ Error Codes

The **Connectify Developer’s Kit (CDK)** uses standardized error codes and messages to help developers quickly identify and resolve issues when interacting with the API.

Each error response includes an HTTP status code and a descriptive error message.

***

#### ⚙️ Error Structure

All errors follow this JSON format:

```json
json

{
  "status": "error",
  "error": {
    "code": "INVALID_API_KEY",
    "message": "Your API key is invalid or expired.",
    "details": "Please verify your credentials in the configuration file."
  }
}
```

***

#### 🚫 Common HTTP Status Codes

| Status Code                   | Meaning          | Description                                       |
| ----------------------------- | ---------------- | ------------------------------------------------- |
| **200 OK**                    | Success          | Request completed successfully                    |
| **201 Created**               | Success          | Resource created successfully                     |
| **400 Bad Request**           | Client Error     | Invalid parameters or malformed request           |
| **401 Unauthorized**          | Auth Error       | Missing or invalid API key or token               |
| **403 Forbidden**             | Access Error     | You don’t have permission to access this resource |
| **404 Not Found**             | Resource Error   | Requested endpoint or resource doesn’t exist      |
| **409 Conflict**              | Conflict Error   | Resource already exists or operation conflict     |
| **429 Too Many Requests**     | Rate Limit Error | API rate limit exceeded — retry after some time   |
| **500 Internal Server Error** | Server Error     | Unexpected error on the server                    |
| **503 Service Unavailable**   | Server Error     | API temporarily unavailable or under maintenance  |

***

#### 💡 Best Practices for Handling Errors

✅ **Log all API errors** — Capture and store error responses for debugging and analytics.\
🔁 **Implement retries** — For transient errors (429, 500, 503), retry after a delay.\
🧩 **Validate inputs** — Ensure request parameters and payloads are properly formatted before submission.\
🔐 **Check authentication** — Use valid API keys or tokens stored securely in environment variables.

***

#### 📚 Next Steps

👉 [⏱️ **Pagination & Rate Limits**](pagination-and-rate-limits.md)
