# 🧠 Example: Unified Remote Integration

This example demonstrates how to integrate the **Connectify SDK** with **Unified Remote**, enabling seamless remote control of devices through automated commands and events.

It combines the concepts you’ve already learned — **API calls, authentication, event handling, and webhook responses** — into a single working scenario.

***

#### 🎯 Objective

To show how developers can use the Connectify SDK to:

* **Authenticate** with their Connectify account.
* **Register devices** through Unified Remote.
* Listen for **remote-triggered events**.
* **Execute custom actions** automatically.

***

#### ⚙️ Setup Requirements

Before you begin, ensure that you have:

* **Connectify SDK** installed.
* **Unified Remote Server** running on your device.
* A valid **API key** and **secret token** from the Connectify Developer Dashboard.
* Node.js (v16+) or Python 3.8+ installed.

***

#### 🧩 Step 1: Initialize SDK and Authenticate

```javascript
javascript

import ConnectifySDK from "connectify-sdk";

const sdk = new ConnectifySDK({
  apiKey: process.env.CONNECTIFY_API_KEY,
  secretKey: process.env.CONNECTIFY_SECRET_KEY,
});

sdk.authenticate()
  .then(() => console.log("✅ SDK authenticated successfully"))
  .catch(err => console.error("❌ Authentication failed:", err));
```

This code establishes a secure connection with Connectify and validates your credentials.

***

#### 🔗 Step 2: Register a Device with Unified Remote

```javascript
javascript

sdk.devices.register({
  deviceId: "remote_001",
  name: "Media Controller",
  type: "unified-remote",
  capabilities: ["play", "pause", "volume"],
});
```

This registers your Unified Remote device in the Connectify network.

***

#### 🛰️ Step 3: Listen for Remote Events

```javascript
javascript

sdk.events.on("remoteCommand", (event) => {
  console.log(`🎮 Command received: ${event.command}`);
});
```

Here, the SDK listens for events such as `play`, `pause`, or `volumeChange` emitted from the remote app.

***

#### ⚡ Step 4: Execute Actions on Event Trigger

<pre class="language-javascript"><code class="lang-javascript"><strong>javascript
</strong><strong>
</strong><strong>sdk.events.on("remoteCommand", (event) => {
</strong>  switch (event.command) {
    case "play":
      sdk.actions.execute("startMedia");
      break;
    case "pause":
      sdk.actions.execute("pauseMedia");
      break;
    case "volumeUp":
      sdk.actions.execute("increaseVolume");
      break;
  }
});
</code></pre>

This code shows how to link Unified Remote inputs to SDK actions automatically.

***

#### ✅ Step 5: Verify the Integration

1. Launch your Unified Remote app.
2. Tap any command — like **Play** or **Volume Up**.
3. Watch your SDK logs — you’ll see matching action confirmations.

***

#### 📘 Summary

This integration example demonstrates:

* How to connect Unified Remote with Connectify SDK.
* Event-driven automation between two systems.
* Real-time response handling and device synchronization.

With this foundation, you can expand the logic to include **multiple devices**, **custom triggers**, or **cloud synchronization** through webhooks.

***

#### 📚 Next Steps

👉 [🧠 Best Practices](broken-reference)
