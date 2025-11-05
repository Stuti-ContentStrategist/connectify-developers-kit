# ❗ Common Issues

Even with a smooth setup, developers may encounter occasional issues while using the **Connectify SDK.**&#x20;

This section highlights frequent problems and provides practical steps to identify and resolve them quickly.

***

#### 🔑 1. Authentication Failures

**Symptoms:**

* API requests return `401 Unauthorized` or `403 Forbidden`.
* Token validation fails during SDK initialization.

**Causes & Fixes:**

* Ensure your **API key or token** is valid and not expired.
* Verify that your **environment variables** (like `CONNECTIFY_API_KEY`) are correctly set.
* Check for **extra spaces or invisible characters** in copied credentials.

💡 Tip: Use the **ping()** or **health-check endpoint** to confirm connectivity.

***

#### 🌐 2. Network or Connection Errors

**Symptoms:**

* Timeouts or “Host Unreachable” messages.
* Requests hang indefinitely.

**Causes & Fixes:**

* Verify that your internet connection is stable.
* Ensure the **API base URL** is correct for your region (e.g., `https://api.connectify.io`).
* Check if your **firewall or proxy settings** block outgoing API requests.
* Retry failed requests using **exponential backoff**.

***

#### ⚙️ 3. SDK Initialization Issues

**Symptoms:**

* “SDK not initialized” or “Configuration missing” errors.

**Causes & Fixes:**

* Make sure `init()` or equivalent setup method is called before any API call.
* Confirm all required environment variables (API key, environment, region) are defined.
* Reinstall the SDK to ensure no missing dependencies.

**Example:**

```bash
bash

pip uninstall connectify-sdk
pip install connectify-sdk
```

***

#### 🔄 4. Version Compatibility

**Symptoms:**

* Functions not recognized or deprecated warnings.

**Causes & Fixes:**

* Check your SDK version using `sdk.version` or package manager commands.
* Compare it with the latest release in the 📞 Support Channels or Changelog.
*   Update to the latest version if needed:

    <pre class="language-bash"><code class="lang-bash"><strong>bash
    </strong><strong>
    </strong><strong>npm update connectify-sdk
    </strong></code></pre>

***

#### 📦 5. Missing Dependencies

**Symptoms:**

* Import or module not found errors.

**Causes & Fixes:**

* Verify installation completed without errors.
* Reinstall the SDK or missing libraries.
* Ensure you’re using compatible versions of your language runtime (e.g., Python 3.8+).

***

#### ⚠️ 6. Unexpected API Responses

**Symptoms:**

* Null or undefined data in API results.
* Missing fields in response objects.

**Causes & Fixes:**

* Check your request parameters and ensure proper formatting (JSON, headers).
* Verify API endpoint versions.
* Log complete request–response cycles for debugging.

***

#### 📚 Next Page

👉 [🕵️ Debugging Techniques](debugging-techniques.md)
