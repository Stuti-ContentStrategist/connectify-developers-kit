# 🧩 Configuration Examples

Once you’ve set up your environment and initialized the **Connectify Software Development Kit (SDK)**, you can customize its configuration to suit your workflow and project structure.

Here are a few common configuration examples for different environments and use cases.

***

#### 🌐 Example 1: Switching Between Sandbox and Production

**Python:**

<pre class="language-python"><code class="lang-python"><strong>python
</strong><strong>
</strong><strong>from connectify import ConnectifySDK
</strong>
env = "sandbox"  # Change to "production" for live use

sdk = ConnectifySDK(
    api_key=os.getenv("CONNECTIFY_API_KEY"),
    api_secret=os.getenv("CONNECTIFY_API_SECRET"),
    environment=env
)
</code></pre>

**Java:**

```java
java

String environment = "sandbox"; // or "production"

ConnectifySDK sdk = new ConnectifySDK.Builder()
    .setApiKey(System.getenv("CONNECTIFY_API_KEY"))
    .setApiSecret(System.getenv("CONNECTIFY_API_SECRET"))
    .setEnvironment(environment)
    .build();
```

**JavaScript:**

<pre class="language-javascript"><code class="lang-javascript"><strong>javascript
</strong><strong>
</strong><strong>const environment = "sandbox"; // or "production"
</strong>
const sdk = new ConnectifySDK({
  apiKey: process.env.CONNECTIFY_API_KEY,
  apiSecret: process.env.CONNECTIFY_API_SECRET,
  environment: environment,
});
</code></pre>

***

#### ⚙️ Example 2: Custom Timeout and Logging

**Python:**

<pre class="language-python"><code class="lang-python"><strong>python
</strong><strong>
</strong><strong>sdk = ConnectifySDK(
</strong>    api_key=os.getenv("CONNECTIFY_API_KEY"),
    api_secret=os.getenv("CONNECTIFY_API_SECRET"),
    environment="production",
    timeout=30,  # seconds
    enable_logging=True
)
</code></pre>

**Java:**

```java
java

ConnectifySDK sdk = new ConnectifySDK.Builder()
    .setApiKey(System.getenv("CONNECTIFY_API_KEY"))
    .setApiSecret(System.getenv("CONNECTIFY_API_SECRET"))
    .setEnvironment("production")
    .setTimeout(30000)
    .enableLogging(true)
    .build();
```

**JavaScript:**

```javascript
javascript

const sdk = new ConnectifySDK({
  apiKey: process.env.CONNECTIFY_API_KEY,
  apiSecret: process.env.CONNECTIFY_API_SECRET,
  environment: "production",
  timeout: 30000,
  enableLogging: true,
});
```

***

#### 🧠 Example 3: Loading Configuration from a JSON File

**config.json:**

```json
json

{
  "apiKey": "your_api_key_here",
  "apiSecret": "your_api_secret_here",
  "environment": "sandbox"
}
```

**Python:**

<pre class="language-python"><code class="lang-python"><strong>python
</strong><strong>
</strong><strong>import json
</strong>from connectify import ConnectifySDK

with open("config.json") as f:
    config = json.load(f)

sdk = ConnectifySDK(**config)
</code></pre>

**JavaScript:**

<pre class="language-javascript"><code class="lang-javascript"><strong>javascript
</strong><strong>
</strong><strong>import fs from "fs";
</strong>import { ConnectifySDK } from "connectify-sdk";

const config = JSON.parse(fs.readFileSync("config.json", "utf-8"));
const sdk = new ConnectifySDK(config);
</code></pre>

***

#### 💡 Tips

* 🧱 Use environment variables for production, and config files for local development.
* 🔐 Always validate config values before SDK initialization.
* ⚡ Keep reusable setup code in a separate module or service for maintainability.

***

#### 📚 **Next Page**

👉 [🔐 Authentication & Security](broken-reference)[\
](environment-setup.md)
