# 🔑 First API Call

After installing and setting up **the Connectify Software Development Kit (SDK)**, you’re ready to make your first API call. This simple example demonstrates how to authenticate and fetch basic account details using your API key.

#### 🐍 Python Example

<pre class="language-python"><code class="lang-python"><strong>python
</strong><strong>
</strong>from connectify import Connectify
sdk = Connectify(api_key="YOUR_API_KEY")
response = sdk.status()
print(response)

</code></pre>

#### **☕ Java** Example

```java
java

import com.connectify.Connectify;

public class Main {
    public static void main(String[] args) {
        Connectify sdk = new Connectify("YOUR_API_KEY");
        System.out.println(sdk.status());
    }
}
```

#### **⚡ JavaScript** Example

<pre class="language-javascript"><code class="lang-javascript"><strong>javascript
</strong><strong>
</strong><strong>import Connectify from "connectify-sdk";
</strong>
const sdk = new Connectify({ apiKey: "YOUR_API_KEY" });
sdk.status().then(console.log);
</code></pre>

#### ✅ **Expected Output:**

```json
json

{
  "status": "connected",
  "version": "2.0.0",
  "timestamp": "2025-11-01T10:32:00Z"
}
```

💡 **Tip:** If you receive an authentication error, double-check that your API key is active and correctly stored in your environment variables.

***

#### 📚 Next Page

👉 [⚙️ Configuration](broken-reference)
