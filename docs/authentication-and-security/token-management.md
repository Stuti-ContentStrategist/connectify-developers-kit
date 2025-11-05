# 🔁 Token Management

After successfully obtaining an access token using **OAuth 2.0**, the **Connectify Software Development Kit (SDK)** helps you manage it efficiently. Tokens authorize your application to perform actions on behalf of a user — so proper management is critical for both security and uptime.

***

#### 🔒 Types of Tokens

| Token Type        | Description                                                   | Lifetime                   |
| ----------------- | ------------------------------------------------------------- | -------------------------- |
| **Access Token**  | Used to authenticate API requests.                            | Short-lived (e.g., 1 hour) |
| **Refresh Token** | Used to generate new access tokens without re-authenticating. | Long-lived (e.g., 30 days) |

***

#### ⚙️ Automatic Token Refresh

The SDK can automatically refresh tokens when they expire, ensuring uninterrupted access.

**Python:**

<pre class="language-python"><code class="lang-python"><strong>python
</strong><strong>
</strong><strong>sdk = ConnectifySDK(
</strong>    api_key=os.getenv("CONNECTIFY_API_KEY"),
    api_secret=os.getenv("CONNECTIFY_API_SECRET"),
    auto_refresh=True
)

response = sdk.api.get_devices()
print("Access token refreshed automatically.")
</code></pre>

**Java:**

<pre class="language-java"><code class="lang-java"><strong>java
</strong><strong>
</strong><strong>ConnectifySDK sdk = new ConnectifySDK.Builder()
</strong>    .setApiKey(System.getenv("CONNECTIFY_API_KEY"))
    .setApiSecret(System.getenv("CONNECTIFY_API_SECRET"))
    .enableAutoRefresh(true)
    .build();

sdk.getDevices();
System.out.println("Access token refreshed automatically.");
</code></pre>

**JavaScript:**

```javascript
javascript

import { ConnectifySDK } from "connectify-sdk";

const sdk = new ConnectifySDK({
  apiKey: process.env.CONNECTIFY_API_KEY,
  apiSecret: process.env.CONNECTIFY_API_SECRET,
  autoRefresh: true,
});

await sdk.api.getDevices();
console.log("Access token refreshed automatically.");
```

***

#### 🔁 Manual Token Refresh

If you prefer to control token refresh manually, use the refresh token method provided by the SDK.

**Python:**

```python
python

new_token = sdk.refresh_token(refresh_token)
print("New access token generated:", new_token)
```

**JavaScript:**

```javascript
javascript

const newToken = await sdk.refreshToken(refreshToken);
console.log("New access token generated:", newToken);
```

***

#### 🧱 Token Storage Best Practices

* 🔐 **Encrypt tokens** before saving them in local or cloud storage.
* 🧼 **Purge old tokens** regularly to reduce security risks.
* 🕒 **Handle expiration gracefully** by checking validity before API calls.
* 🧠 **Use refresh tokens carefully** — store them only in secure environments (never in browser storage).

***

#### 📚 **Next Page**

👉 [🛡️ Security Best Practices](security-best-practices.md)
