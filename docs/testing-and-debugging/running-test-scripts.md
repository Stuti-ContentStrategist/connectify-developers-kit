# 🧪 Running Test Scripts

Before deploying your Connectify SDK integration, it’s essential to test its functionality and verify that the APIs, authentication, and configurations work as expected.

This section walks you through how to set up and execute test scripts across different environments.

***

#### ⚙️ 1. Prerequisites

Ensure that:

* The **SDK is properly installed** and initialized.
* You have valid **API keys or access tokens**.
* Your environment variables (e.g., `API_BASE_URL`, `SDK_KEY`) are correctly configured.

💡 _Tip:_ Use a **sandbox environment** whenever possible to avoid impacting production data.

***

#### 💻 2. Example: Basic Connectivity Test

**Python Example:**

```python
python

from connectify_sdk import Client

client = Client(api_key="your_api_key")

response = client.ping()
print(response.status)
```

**Expected Output:**

```
plain text

✅ SDK connected successfully.
```

***

#### ☕ Java Example

```java
java

ConnectifyClient client = new ConnectifyClient("your_api_key");
ApiResponse response = client.ping();
System.out.println(response.getStatus());
```

***

#### ⚡ JavaScript Example

```javascript
javascript

import { ConnectifyClient } from "connectify-sdk";

const client = new ConnectifyClient({ apiKey: "your_api_key" });
const response = await client.ping();
console.log(response.status);
```

***

#### 🧾 3. Validate API Behavior

After confirming connectivity, run endpoint-specific tests:

* **Authentication Test:** Verify login or token exchange.
* **Data Retrieval Test:** Fetch a list of devices, events, or triggers.
* **Error Handling Test:** Use invalid credentials to ensure proper error responses.

💡 _Tip:_ Always test with both **valid** and **invalid** data to confirm robustness.

***

#### 🔄 4. Automate Testing

* Integrate SDK tests into your **CI/CD pipeline**.
* Use frameworks like **Pytest**, **JUnit**, or **Mocha** depending on the language.
* Schedule recurring tests to catch regressions early.

Example (Python + Pytest):

```bash
bash

pytest tests/test_connectify_client.py
```

***

#### 📊 5. Analyze Results

* Log all test outputs for reference.
* Identify failures early to isolate configuration or code issues.
* Re-run only the failed tests after fixes to confirm resolution.

***

#### &#x20;📚 Next Page

👉 [❗ Common Issues](common-issues.md)
