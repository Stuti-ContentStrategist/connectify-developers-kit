# ✍️ Signature Verification

Every webhook request from **Connectify** includes a **signature header** to help you confirm that the payload was not tampered with and originated from a trusted Connectify source.

***

#### 🔐 Why Signature Verification Matters

* ✅ **Verifying the signature ensures that:**
  * 🔒 The webhook request genuinely came from **Connectify**
  * 🧩 The payload data was **not modified** in transit
  * 🛡️ Your system is **protected from spoofed or malicious** webhook calls

***

#### 🧾 Signature Header

Each webhook request includes a custom header:

<pre class="language-bash"><code class="lang-bash"><strong>bash
</strong><strong>
</strong><strong>X-Connectify-Signature: sha256=ac1f4c7e5f28a3b97a0c11d8a6c3fdfb1d5a73c8b2f1b5d9e6a9e8df2a4f1b9c
</strong></code></pre>

The value is a **SHA-256 HMAC** hash generated using:

```
plain text

HMAC(secret_key, request_body)
```

***

#### ⚙️ Verification Steps

1. **Retrieve the signature** from the `X-Connectify-Signature` header.
2. **Compute your own hash** of the received body using your Connectify webhook secret.
3. **Compare** your computed hash with the one from the header.
4. **Accept the webhook** only if they match exactly.

***

#### 💻 Example (Node.js)

```javascript
javascript

import crypto from "crypto";

const verifySignature = (req, secret) => {
  const signature = req.headers["x-connectify-signature"];
  const payload = JSON.stringify(req.body);

  const computedHash = crypto
    .createHmac("sha256", secret)
    .update(payload)
    .digest("hex");

  return crypto.timingSafeEqual(
    Buffer.from(signature.replace("sha256=", "")),
    Buffer.from(computedHash)
  );
};
```

***

💡 **Tips**

* &#x20;Always use **timing-safe comparison** to prevent timing attacks.&#x20;
* Store webhook secrets securely (e.g., in environment variables).
* Rotate webhook secrets periodically for enhanced protection.

***

#### 📚 Next Page

👉 [🧪 **Testing Webhooks**](testing-webhooks.md)
