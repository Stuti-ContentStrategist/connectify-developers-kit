# 🧠 Using SDK in Node.js

The **Connectify JavaScript SDK** can be easily integrated into any **Node.js** application to interact with Connectify APIs.

This section shows you how to initialize the SDK and make your first API call from a Node environment.

***

#### ⚙️ Basic Setup

Import the SDK and create a client instance using your API credentials:

```javascript
javascript

import Connectify from "connectify-sdk";

const client = new Connectify({
  apiKey: process.env.CONNECTIFY_API_KEY,
  apiSecret: process.env.CONNECTIFY_API_SECRET,
  environment: "production",
});

console.log("Connectify SDK initialized successfully!");
```

If you’re using CommonJS:

```javascript
javascript

const Connectify = require("connectify-sdk");

const client = new Connectify({
  apiKey: process.env.CONNECTIFY_API_KEY,
  apiSecret: process.env.CONNECTIFY_API_SECRET,
});
```

***

#### 📡 Example — Fetch Devices

```javascript
javascript

async function getDevices() {
  const devices = await client.devices.getAll();
  console.log("Connected devices:", devices);
}

getDevices();
```

***

#### 💡 Tip

Use **environment variables** (via `.env` files or deployment secrets) instead of hard-coding API credentials.\
You can use libraries like `dotenv` for simple setup:

```bash
bash

npm install dotenv
```

<pre class="language-javascript"><code class="lang-javascript"><strong>javascript
</strong><strong>
</strong><strong>import "dotenv/config";
</strong></code></pre>

***

#### 📚 Next Step

👉 [🌐 **Using SDK in Browser**](using-sdk-in-browser.md)
