# ⚡ SDK Initialization

Once your environment is configured, you’re ready to initialize the **Connectify Developer’s Kit (CDK)** in your project. Initialization connects your SDK instance with your Connectify account, enabling authenticated API calls and integrations.

#### 🐍 Python

```python
python

from connectify import ConnectifySDK

# Initialize SDK
sdk = ConnectifySDK(
    api_key="your_api_key_here",
    api_secret="your_api_secret_here",
    environment="production"
)

print("Connectify SDK initialized successfully!")
```

***

#### ☕ Java

```java
java

import com.connectify.sdk.ConnectifySDK;

public class Main {
    public static void main(String[] args) {
        ConnectifySDK sdk = new ConnectifySDK.Builder()
            .setApiKey("your_api_key_here")
            .setApiSecret("your_api_secret_here")
            .setEnvironment("production")
            .build();

        System.out.println("Connectify SDK initialized successfully!");
    }
}
```

***

#### ⚡ JavaScript

```javascript
javascript

import { ConnectifySDK } from "connectify-sdk";

// Initialize SDK
const sdk = new ConnectifySDK({
  apiKey: "your_api_key_here",
  apiSecret: "your_api_secret_here",
  environment: "production",
});

console.log("Connectify SDK initialized successfully!");
```

***

#### 🔍 Notes

* Always use **securely stored credentials** — avoid hardcoding secrets directly in your code.
* Set your environment to `"sandbox"` during testing to prevent changes in production.
* Initialization should occur **once** at the start of your application to ensure consistent API access.

💡 **Tip:** If you experience authentication issues, revisit your environment variables in the previous section.

***

#### 📚 **Next Page**

👉 [🔐 API Keys & Secrets](api-keys-and-secrets.md)\
