# 📦 Payload Format

Every webhook sent by **Connectify** follows a consistent **JSON payload structure**.\
This ensures that your application can reliably parse, validate, and process incoming events — regardless of the type of notification being received.

***

#### 🧱 Standard Payload Structure

Each webhook payload includes:

* **event** — The name of the event (e.g., `device.online`).
* **data** — The event-specific details.
* **timestamp** — The UTC time the event occurred.
* **id** — A unique identifier for the event (used to prevent duplicates).
* **signature** — A hash used to verify authenticity (included in the request header).

**Example Payload:**

```json
json

{
  "id": "evt_8f92d3b7c1",
  "event": "device.online",
  "timestamp": "2025-11-01T10:12:00Z",
  "data": {
    "device_id": "dev123",
    "device_name": "Smart Plug",
    "status": "online"
  }
}
```

***

#### 📬 Example Server Log

When your endpoint receives the webhook, it might log something like:

```bash
bash

[INFO] Webhook received: device.online for Smart Plug at 2025-11-01T10:12:00Z
```

***

#### 🧠 Best Practices

✅ **Always validate payload signatures** before processing.\
⚙️ **Store webhook IDs** to detect and ignore duplicate events.\
📦 **Use structured logging** for tracking and debugging webhook activity.\
🛡️ **Respond quickly** (within 5 seconds) to confirm receipt and avoid retries.

💡 **Tip:** Connectify may retry webhook delivery up to **3 times** if it doesn’t receive a `2xx` response.

***

#### 📚 Next Page

👉 [✍️ **Signature Verification**](signature-verification.md)
