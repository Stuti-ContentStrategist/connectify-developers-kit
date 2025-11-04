# 🎭 Mocking API Responses

Mocking API responses allows you to **simulate SDK behavior** without making live calls to the production API. It’s a crucial technique for **testing integrations, running CI/CD pipelines, and avoiding API rate limits**.

***

#### 🧰 Why Use Mocking?

* ✅ **Faster testing:** Avoid waiting for network responses.
* 🧪 **Isolated environment:** Test SDK logic without depending on external services.
* 💸 **No usage costs:** Prevent consuming API quota during development.
* 🧱 **Predictable results:** Control responses for consistent, repeatable test cases.

***

#### 🧩 1. Using the Built-In Mock Mode

Connectify SDK includes a **mock mode** that automatically returns pre-configured responses.

**Example (JavaScript):**

```javascript
javascript

import { ConnectifyClient } from "connectify-sdk";

const client = new ConnectifyClient({
  apiKey: "test_key",
  mock: true // Enables mock mode
});

const devices = await client.getDevices();
console.log(devices);
```

**Example (Python):**

<pre class="language-python"><code class="lang-python"><strong>python
</strong><strong>
</strong><strong>from connectify_sdk import Client
</strong>
client = Client(api_key="test_key", mock=True)
devices = client.get_devices()
print(devices)
</code></pre>

💡 _Tip:_ Use this mode to test UI workflows before backend integration is ready.

***

#### ⚙️ 2. Mocking with External Tools

If your SDK does not support native mocking, you can use external libraries or services.

**🧱 For JavaScript**

Use **MSW (Mock Service Worker)** or **nock**:

```javascript
javascript

import nock from "nock";

nock("https://api.connectify.io")
  .get("/devices")
  .reply(200, [{ id: "mock1", name: "Test Device" }]);
```

**🐍 For Python**

Use **responses** or **pytest-httpserver**:

<pre class="language-python"><code class="lang-python"><strong>python
</strong><strong>
</strong><strong>import responses
</strong>import requests

@responses.activate
def test_get_devices():
    responses.add(
        responses.GET,
        "https://api.connectify.io/devices",
        json=[{"id": "mock1", "name": "Test Device"}],
        status=200,
    )
    resp = requests.get("https://api.connectify.io/devices")
    print(resp.json())
</code></pre>

***

#### 🔄 3. Recording and Replaying API Calls

To make tests more realistic, you can **record real API responses** once and replay them later.

* Use **VCR.py** (Python) or **Polly.js** (JavaScript).
* The SDK will behave exactly as if it’s calling the API, but responses come from a saved cassette.

**Example (Python + VCR):**

```python
python

import vcr

@vcr.use_cassette('fixtures/device_list.yml')
def test_devices():
    client.get_devices()
```

***

#### 🧠 4. Integrating with CI/CD

Mocking allows SDK tests to run **without network dependencies** inside CI/CD environments.

* Configure mock mode in your test configuration (e.g., `.env.test`).
* Run tests using mocked responses to ensure consistent build outcomes.

***

#### 🚀 5. Best Practices

* Store mock data in a dedicated `/mocks` directory.
* Name mock files after the endpoint (e.g., `get_devices_mock.json`).
* Regularly update mocks when API schema changes.
* Avoid including sensitive data in mock files.

***

#### 📚 Next Page

👉 🩺 Troubleshooting
