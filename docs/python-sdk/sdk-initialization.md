# ⚙️ SDK Initialization

After installing the **Connectify Developer’s Kit (CDK) Python SDK**, you’ll need to initialize it to begin interacting with the Connectify Platform.

Initialization sets up authentication, establishes a connection, and prepares the SDK for making API calls.

#### 🔑 Step 1: Import the SDK

Start by importing the SDK in your Python script:

```python
python

from connectify_sdk import ConnectifyClient
```

#### ⚙️ Step 2: Initialize the Client

You can initialize the client by providing your API key (or OAuth token) and environment configuration:

```python
python

client = ConnectifyClient(
    api_key="your_api_key_here",
    environment="production"  # or "sandbox"
)
```

💡 **Tip:** Use `"sandbox"` mode while testing to avoid impacting live data.

#### 🧱 Step 3: Verify the Connection

Once initialized, you can verify that your client is connected and authorized by making a simple API call:

```python
python

status = client.get_status()
print(status)
```

Expected output:

```bash
bash

{'status': 'connected', 'environment': 'production'}
```

#### 🔐 Step 4: Using Environment Variables (Recommended)

For better security, avoid hardcoding API keys directly in your code.\
Store them in environment variables instead:

```bash
# macOS/Linux
export CONNECTIFY_API_KEY="your_api_key_here"

# Windows (PowerShell)
setx CONNECTIFY_API_KEY "your_api_key_here"
```

Then update your initialization code:

```python
import os
from connectify_sdk import ConnectifyClient

client = ConnectifyClient(
    api_key=os.getenv("CONNECTIFY_API_KEY"),
    environment="production"
)
```

#### 💡 Best Practices

* Always **store secrets securely** (never in version control).
* Use **different environments** (`sandbox`, `staging`, `production`) for development and deployment.
* **Log connection errors** during initialization for easier debugging.

***

✅ **You’re ready to go!**\
Your SDK is now initialized and ready to make your first API call.

***

#### 📚 **Next Page**

👉 [💬 Example API Calls](example-api-calls.md)
