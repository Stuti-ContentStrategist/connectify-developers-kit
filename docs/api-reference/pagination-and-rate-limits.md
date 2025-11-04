# ⏱️ Pagination & Rate Limits

To ensure efficient data retrieval and maintain API performance, the **Connectify Developer’s Kit (CDK)** implements **pagination** for large datasets and **rate limiting** to prevent excessive requests.

Understanding and handling both correctly ensures smoother, faster, and more reliable integrations.

***

#### 📄 Pagination

When you request a large collection (like devices, users, or events), the API returns results in **pages** instead of sending all data at once.

**Example Request:**

```bash
bash

GET https://api.connectify.io/v1/devices?limit=10&offset=20
Authorization: Bearer <your_api_key>
```

**Parameters:**

| Parameter  | Type    | Description                                 |
| ---------- | ------- | ------------------------------------------- |
| **limit**  | Integer | Number of items per page                    |
| **offset** | Integer | Starting index for the next page of results |

**Example Response:**

<pre class="language-json"><code class="lang-json"><strong>json
</strong><strong>
</strong><strong>{
</strong>  "devices": [
    { "id": "dev121", "name": "Smart Plug A" },
    { "id": "dev122", "name": "Smart Plug B" }
  ],
  "pagination": {
    "limit": 10,
    "offset": 20,
    "total": 52
  }
}
</code></pre>

💡 **Tip:** Use the `limit` and `offset` values from the response to load the next batch of results efficiently.

***

#### 🚦 Rate Limits

To maintain optimal API performance, Connectify enforces request limits based on your **API key** and **plan type**.

| Plan Type      | Limit        | Window        |
| -------------- | ------------ | ------------- |
| **Free**       | 60 requests  | per minute    |
| **Pro**        | 600 requests | per minute    |
| **Enterprise** | Custom       | per agreement |

If you exceed your rate limit, you’ll receive a **429 Too Many Requests** response.

**Example Error:**

```json
json

{
  "status": "error",
  "error": {
    "code": "RATE_LIMIT_EXCEEDED",
    "message": "Too many requests. Please try again after 60 seconds."
  }
}
```

***

#### 🧭 Best Practices

⚙️ **Throttle requests** — Implement short delays or backoff mechanisms between calls.\
📊 **Monitor usage** — Use dashboard analytics or logs to track request frequency.\
🔁 **Retry gracefully** — When receiving a 429 response, wait for the retry window before resending.

***

#### 📚 Next Page

👉 [💬 Webhooks](broken-reference)

