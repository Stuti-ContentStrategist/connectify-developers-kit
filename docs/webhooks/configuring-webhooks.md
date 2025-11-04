# ⚙️ Configuring Webhooks

Before your application can receive real-time updates from **Connectify**, you need to **register and configure** one or more webhook endpoints. Each endpoint corresponds to a unique URL on your server where Connectify sends HTTP `POST` requests whenever an event occurs.

***

#### 🧭 Steps to Configure a Webhook

1. **Open your Connectify Developer Console**
   * Navigate to **Integrations → Webhooks**.
2. **Add a New Webhook**
   * Enter your server’s **callback URL** (for example: `https://api.yourapp.com/webhooks/connectify`).
   * Choose the **events** you want to subscribe to (e.g., `device.online`, `automation.triggered`, `user.updated`).
3. **Save and Test**
   * Click **“Test Webhook”** to send a sample payload and confirm successful delivery.
   * If your endpoint responds with **HTTP 200 OK**, the webhook is verified successfully.

***

#### 🧪 Example Request

```bash
bash

POST https://api.yourapp.com/webhooks/connectify
Content-Type: application/json
Signature: t=1730444444,v1=dcbbab7b1f32e9e4...

{
  "event": "device.online",
  "data": {
    "device_id": "dev123",
    "status": "online",
    "timestamp": "2025-11-01T09:35:00Z"
  }
}
```

***

#### 🧱 Endpoint Requirements

| Requirement  | Description                                       |
| ------------ | ------------------------------------------------- |
| **HTTPS**    | Only secure (HTTPS) endpoints are supported       |
| **Response** | Must return HTTP 2xx within 5 seconds             |
| **Retries**  | Failed requests are retried up to 3 times         |
| **Timeouts** | Requests exceeding 5 seconds are marked as failed |

💡 **Tip:** Always log incoming webhook requests for easier debugging and traceability.

***

#### 📚 Next Steps

👉 [🔔 **Event Types**](event-types.md)
