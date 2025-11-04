# ⚙️ SDK Initialization

Once you’ve installed the Connectify Java SDK, the next step is to **initialize it** in your project. Initialization sets up authentication, configuration, and the client environment required for making API calls.

***

#### 🔧 Basic Setup

Start by importing the SDK and creating an instance of the Connectify client.\
You’ll need your **API key** and **secret**, which can be obtained from your Connectify Developer Console.

```java
java

import com.connectify.sdk.ConnectifyClient;

public class Main {
    public static void main(String[] args) {
        ConnectifyClient client = new ConnectifyClient.Builder()
            .setApiKey("YOUR_API_KEY")
            .setApiSecret("YOUR_API_SECRET")
            .setEnvironment("production")
            .build();

        System.out.println("Connectify SDK initialized successfully!");
    }
}
```

***

#### ⚙️ Environment Options

You can initialize the SDK for different environments:

* 🧱 **Development:** Local testing and debugging
* 🌐 **Staging:** Pre-production testing
* 🚀 **Production:** Live deployments

Example:

```java
java

.setEnvironment("staging")
```

***

#### 💡 Tip

Store your credentials securely — never hard-code API keys directly in source files.\
Use environment variables or encrypted configuration files instead.

***

#### 📚 Next Page

👉 [💬 **API Usage Examples**](api-usage-examples.md)
