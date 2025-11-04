# 🔑 First API Call

Once **this SDK** is installed, make your first API call to confirm everything is working.

#### 🐍 Python

<pre class="language-python"><code class="lang-python"><strong>python
</strong><strong>
</strong>from connectify import Connectify
sdk = Connectify(api_key="YOUR_API_KEY")
response = sdk.status()
print(response)

</code></pre>

**☕ Java**

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

**⚡ JavaScript**

<pre class="language-javascript"><code class="lang-javascript"><strong>javascript
</strong><strong>
</strong><strong>import Connectify from "connectify-sdk";
</strong>
const sdk = new Connectify({ apiKey: "YOUR_API_KEY" });
sdk.status().then(console.log);
</code></pre>

✅ **Expected Output:**

```json
json

{
  "status": "connected",
  "version": "2.0.0",
  "timestamp": "2025-11-01T10:32:00Z"
}
```

💡 **Tip:** If the connection fails, check your API key, network access, and firewall settings.

***

#### 📚 Next Page

👉 [⚙️ Configuration](broken-reference)
