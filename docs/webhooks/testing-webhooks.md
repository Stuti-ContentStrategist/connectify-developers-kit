# 🧪 Testing Webhooks

Before going live, it’s essential to **test your webhook** setup to make sure events are delivered, verified, and handled correctly. Connectify provides multiple ways to test and debug your webhook integration safely.

***

#### 🧰 Available Testing Options

**1. Using Connectify Dashboard**

You can trigger **sample webhook events** from the Connectify Developer Dashboard.

* Go to **Webhooks → Test Delivery**.
* Select an event type (e.g., `device.connected`, `trigger.executed`).
* Inspect your endpoint logs to confirm successful receipt.

**2. Using Command Line (cURL)**

You can also simulate webhook deliveries manually:

```bash
bash

curl -X POST https://yourdomain.com/webhook-endpoint \
  -H "Content-Type: application/json" \
  -H "X-Connectify-Signature: sha256=your_generated_signature" \
  -d '{"event":"device.connected","timestamp":"2025-11-01T09:00:00Z"}'
```

This helps validate how your endpoint processes payloads and verifies signatures.

***

💡 **Tips**

* Log both the **headers and body** for each webhook request (only in development).
* Validate **response codes** — Connectify expects a `2xx` response for successful delivery.
* Retry failed deliveries until they pass, ensuring **idempotency** in your webhook logic.

***

#### 🧠 Recommended Tools

* 🧭 **ngrok** — expose your local server to the internet for live testing.
* 🪶 **RequestBin** — capture and inspect webhook payloads easily.
* 🧰 **Postman Mock Server** — simulate endpoints for testing webhook flows.

***

#### 📚 Next Page

👉 [🧩 Integration Guides](broken-reference)
