# 📤 Request & Response Formats

All **Connectify API** requests and responses follow a **RESTful JSON** format to ensure consistency, readability, and ease of integration across languages and platforms.

This section outlines how to structure your requests and interpret responses when communicating with the Connectify Developer’s Kit (CDK).

***

#### 📨 Request Format

Each request typically includes:

1. **HTTP Method** — The operation type (GET, POST, PUT, DELETE).
2. **Endpoint URL** — The API resource you’re targeting.
3. **Headers** — Required authentication and content type information.
4. **Body (optional)** — JSON payload for data submission (POST/PUT).

**Example (POST /devices):**

```bash
bash

POST https://api.connectify.io/v1/devices
Content-Type: application/json
Authorization: Bearer <your_api_key>

{
  "name": "Smart Plug",
  "type": "IoT",
  "status": "active"
}
```

***

#### 📦 Response Format

The Connectify API returns structured JSON responses that include:

* **status** — Indicates whether the request was successful.
* **data** — Contains the resource or operation result.
* **error** — Provides details in case of failure.

**Example (Success Response):**

```json
json

{
  "status": "success",
  "data": {
    "id": "dev123",
    "name": "Smart Plug",
    "status": "active"
  }
}
```

**Example (Error Response):**

<pre class="language-json"><code class="lang-json"><strong>json
</strong><strong>
</strong><strong>{
</strong>  "status": "error",
  "error": {
    "code": "INVALID_API_KEY",
    "message": "Your API key is invalid or missing."
  }
}
</code></pre>

***

#### ⚙️ Headers

| Header          | Description              | Example                 |
| --------------- | ------------------------ | ----------------------- |
| `Content-Type`  | Specifies data format    | `application/json`      |
| `Authorization` | API key or bearer token  | `Bearer <your_api_key>` |
| `Accept`        | Expected response format | `application/json`      |

💡 **Tip:** Always use HTTPS for secure data transmission and verify your API responses to handle potential errors gracefully.

***

#### 📚 Next Page

👉 [❌ **Error Codes**](error-codes.md)
