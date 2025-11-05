# 🔗 Integration with External APIs

The **Connectify SDK** can work seamlessly alongside **third-party APIs** to extend your application’s functionality. You can combine data, automate cross-platform actions, or synchronize events between Connectify and external services — all within a unified workflow.

#### 📘 **What You’ll Learn**

In this section, you’ll learn how to:

* 🌐 **Connect and exchange data** between Connectify and external APIs
* 🔐 **Authenticate and manage** multiple API tokens securely
* ⚙️ **Chain API requests** for enhanced automation
* 🛡️ **Handle errors and rate limits** effectively

***

#### 🧭 Prerequisites

Before you begin, make sure that you have:

* The **Connectify SDK** installed and initialized.
* Access to an external REST API (e.g., Slack, Trello, or custom API).
* Valid API credentials for both Connectify and the external service.

***

#### ⚙️ Integration Steps

**1. Fetch Data from an External API**

Here’s an example of integrating **Slack API** with Connectify SDK:

```javascript
javascript

import fetch from "node-fetch";
import { Connectify } from "connectify-sdk";

const sdk = new Connectify({
  apiKey: process.env.CONNECTIFY_API_KEY,
  secret: process.env.CONNECTIFY_SECRET,
});

async function notifyDeviceStatus() {
  const devices = await sdk.devices.list();

  const slackMessage = {
    text: `Current Active Devices: ${devices.length}`,
  };

  await fetch("https://slack.com/api/chat.postMessage", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      Authorization: `Bearer ${process.env.SLACK_TOKEN}`,
    },
    body: JSON.stringify({
      channel: "#connectify-alerts",
      ...slackMessage,
    }),
  });

  console.log("Device status sent to Slack!");
}

notifyDeviceStatus();
```

***

**2. Chain Multiple API Calls**

You can combine responses from both APIs to automate workflows.\
For example, when a device goes offline, Connectify can trigger an external API call to restart a process or send an alert:

```javascript
javascript

sdk.on("device_offline", async (device) => {
  await fetch("https://api.thirdparty.com/restart", {
    method: "POST",
    headers: { Authorization: `Bearer ${process.env.THIRD_PARTY_TOKEN}` },
    body: JSON.stringify({ deviceId: device.id }),
  });

  console.log(`Restart triggered for ${device.name}`);
});
```

***

#### ✅ Verification

* Check **both platforms’ dashboards or logs** for successful request/response updates.
* Verify that **API tokens are valid** and have appropriate scopes.
* **Review rate limits** and handle retries gracefully for large-scale integrations.

***

#### 🧠 Best Practices

* Use **environment variables** for all credentials.
* **Log API responses selectively** — avoid storing sensitive data.
* **Cache common responses** to reduce API calls.
* Use **retry policies** or exponential backoff for transient errors.

***

#### 📚 Next Page

👉 [🧠 Example: Unified Remote Integration](example-unified-remote-integration.md)
