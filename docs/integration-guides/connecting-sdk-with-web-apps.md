# 🌐 Connecting SDK with Web Apps

The **Connectify SDK** can be easily integrated into your web applications to enable real-time device control, data exchange, and event automation directly from the browser or backend services.

This **section** walks you through how to:

* ⚙️ **Initialize the SDK** in both frontend (browser) and backend (Node.js) environments
* 🔐 **Authenticate users** and manage API keys securely
* 🔄 **Send and receive data** between your app and the Connectify platform
* ✅ **Test and verify** successful integration

***

#### 🧭 Prerequisites

Before you begin, make sure that you have:

* The **Connectify SDK** installed (via npm or yarn).
* A valid **API key** and **secret** from your Connectify Developer Dashboard.
* Basic familiarity with JavaScript or TypeScript.

***

#### ⚙️ Integration Steps

**1. Install the SDK**

```bash
bash

npm install connectify-sdk
```

**2. Initialize in Your Web App**

```javascript
javascript

import { Connectify } from "connectify-sdk";

const sdk = new Connectify({
  apiKey: process.env.CONNECTIFY_API_KEY,
  secret: process.env.CONNECTIFY_SECRET,
});
```

**3. Make Your First Call**

```javascript
javascript

sdk.devices.list().then((devices) => {
  console.log("Connected Devices:", devices);
});
```

**4. Handle Events (Optional)**

```javascript
javascript

sdk.on("device_connected", (device) => {
  console.log(`${device.name} just came online!`);
});
```

***

#### ✅ Verification

* Ensure the **browser console or server log displays** device information.
* If authentication fails, **double-check your API key** and secret.
* Test event triggers through your **Connectify Dashboard** to verify connectivity.

***

#### 📚 Next Page

👉 [🔧 Using SDK in CI/CD](using-sdk-in-ci-cd.md)
