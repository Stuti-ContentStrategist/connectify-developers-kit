# 🔐 API Keys & Secrets

The **Connectify Developer’s Kit (CDK)** uses API keys and secrets to authenticate your application and authorize API requests. These credentials ensure that your integrations communicate securely with the Connectify platform.

#### 🧾 Understanding Your Credentials

* **API Key:** Identifies your application when making API calls.
* **API Secret:** Verifies the authenticity of your requests. Keep it strictly confidential.
* **Environment:** Specifies whether you’re using the `sandbox` (test) or `production` (live) environment.

Example configuration:

```bash
CONNECTIFY_API_KEY=your_api_key_here
CONNECTIFY_API_SECRET=your_api_secret_here
CONNECTIFY_ENV=sandbox
```

💡 **Tip:** Use `sandbox` during development and testing to avoid affecting production data.

***

#### 🛠️ Managing API Keys

1. **Generate Keys:**\
   Log in to your **Connectify Developer Dashboard** → navigate to **API Access** → click **Generate New Key Pair**.
2. **Store Securely:**
   * Save your keys in a `.env` file or encrypted secrets manager.
   * Never expose them in client-side code (such as browser-based JavaScript).
3. **Rotate Periodically:**\
   Regularly regenerate keys and update them in your environment to enhance security.

***

#### 🧰 Using Keys in Code

**Python:**

```python
sdk = ConnectifySDK(
    api_key=os.getenv("CONNECTIFY_API_KEY"),
    api_secret=os.getenv("CONNECTIFY_API_SECRET"),
    environment=os.getenv("CONNECTIFY_ENV")
)
```

**Java:**

```java
ConnectifySDK sdk = new ConnectifySDK.Builder()
    .setApiKey(System.getenv("CONNECTIFY_API_KEY"))
    .setApiSecret(System.getenv("CONNECTIFY_API_SECRET"))
    .setEnvironment(System.getenv("CONNECTIFY_ENV"))
    .build();
```

**JavaScript:**

```javascript
const sdk = new ConnectifySDK({
  apiKey: process.env.CONNECTIFY_API_KEY,
  apiSecret: process.env.CONNECTIFY_API_SECRET,
  environment: process.env.CONNECTIFY_ENV,
});
```

***

#### 🚨 Best Practices

* 🔒 **Never commit secrets** to version control (GitHub, GitLab, etc.).
* 🔁 **Rotate keys** regularly for improved security.
* 🧱 **Use environment variables** instead of hardcoding credentials.
* 🕵️ **Restrict access** to keys based on role or environment.
