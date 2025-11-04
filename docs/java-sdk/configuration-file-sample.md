# 🧩 Configuration File Sample

The **Connectify Java SDK** allows you to store your API credentials and environment settings in a configuration file. This helps you separate sensitive data from your codebase and simplifies deployment across environments.

***

#### ⚙️ Sample Configuration File (`connectify-config.json`)

```json
json

{
  "apiKey": "YOUR_API_KEY",
  "apiSecret": "YOUR_API_SECRET",
  "environment": "production",
  "logLevel": "INFO"
}
```

**Configuration Options:**

| Key           | Description                                                           | Example      |
| ------------- | --------------------------------------------------------------------- | ------------ |
| `apiKey`      | Your Connectify API key                                               | `"1234abcd"` |
| `apiSecret`   | Your Connectify API secret                                            | `"abcd1234"` |
| `environment` | Specifies the environment (`development`, `staging`, or `production`) | `"staging"`  |
| `logLevel`    | Controls SDK logging level (`DEBUG`, `INFO`, `ERROR`)                 | `"DEBUG"`    |

***

#### 🧩 Loading the Configuration File

You can load your configuration file at startup:

```java
java

import com.connectify.sdk.ConnectifyClient;
import com.connectify.sdk.config.ConfigLoader;

public class ConfigExample {
    public static void main(String[] args) {
        ConnectifyClient client = new ConfigLoader()
            .load("connectify-config.json")
            .buildClient();

        System.out.println("SDK configured successfully using config file!");
    }
}
```

***

#### 💡 Tip

Keep your configuration files **outside your version control system** (e.g., add them to `.gitignore`) to protect sensitive credentials.

***

#### 📚 Next Page

👉 [🔄 API Reference](broken-reference)
