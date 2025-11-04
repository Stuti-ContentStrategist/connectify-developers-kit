# 🕵️ Debugging Techniques

Effective debugging helps you trace, isolate, and fix issues quickly when working with the Connectify SDK.

This section covers best practices, recommended tools, and techniques to make troubleshooting faster and more reliable.

***

#### 🔍 1. Enable Debug Mode

Most Connectify SDKs include a **debug or verbose mode** that logs detailed runtime information.

**Example (Python):**

<pre class="language-python"><code class="lang-python"><strong>python
</strong><strong>
</strong><strong>from connectify_sdk import Client
</strong>
client = Client(api_key="your_api_key", debug=True)
client.connect()
</code></pre>

**Example (JavaScript):**

```javascript
javascript

const client = new ConnectifyClient({
  apiKey: "your_api_key",
  debug: true
});
client.connect();
```

💡 _Tip:_ Debug mode helps capture request/response cycles, API URLs, and payload data — invaluable for diagnosing silent failures.

***

#### 🧾 2. Inspect Logs

* Review **SDK logs** generated during initialization and API calls.
* Filter logs by severity (e.g., ERROR, WARN) to focus on critical issues.
* Enable **timestamped logs** for tracking issues in distributed environments.

**Example (Log Entry):**

```json
json

{
  "timestamp": "2025-11-01T10:15:00Z",
  "level": "ERROR",
  "module": "DeviceManager",
  "message": "Timeout while fetching device status",
  "request_id": "req_56789"
}
```

***

#### 🧩 3. Check Configuration and Environment Variables

Misconfigured environment variables often cause authentication or initialization issues.

*   Run a quick check in your terminal:

    <pre class="language-bash"><code class="lang-bash"><strong>bash
    </strong><strong>
    </strong><strong>echo $CONNECTIFY_API_KEY
    </strong>echo $CONNECTIFY_ENV
    </code></pre>
* Ensure no sensitive values are missing or mistyped.
* Verify file permissions if using `.env` files.

***

#### 🧠 4. Validate API Requests

Capture outbound API calls to ensure the request structure matches the documentation.

* Use **Postman**, **cURL**, or browser **Network Inspector** to view:
  * Endpoint URL
  * Headers
  * Payload structure
  * Response body and status code

💡 _Tip:_ Compare a successful and a failed request to pinpoint the mismatch.

***

#### ⚙️ 5. Isolate Problem Areas

Break your code into smaller testable units:

* Start with SDK initialization only.
* Gradually add API calls to identify where failures begin.
* Use try–catch or equivalent exception handling to log specific errors.

**Example:**

```javascript
javascript

try {
  const response = await client.getDevices();
} catch (error) {
  console.error("Error fetching devices:", error.message);
}
```

***

#### 📊 6. Use External Debugging Tools

* **Postman Console:** Inspect raw HTTP traffic.
* **Wireshark or Fiddler:** Analyze network-level data for latency or dropped connections.
* **IDE Debuggers (VS Code, PyCharm, IntelliJ):** Step through SDK execution line by line.

***

#### 🧪 7. Verify SDK and API Versions

Ensure your SDK version matches the API version used in production.\
Incompatible versions often cause undefined fields or errors in response parsing.

**Example:**

```bash
bash

connectify-sdk --version
```

***

#### 📚 Next Page

👉 [🎭 Mocking API Responses](mocking-api-responses.md)
