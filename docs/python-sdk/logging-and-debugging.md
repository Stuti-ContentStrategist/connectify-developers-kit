# 🧾 Logging & Debugging

Effective **logging and debugging** are key to maintaining reliable applications and understanding how your SDK interacts with the Connectify Platform.\
The **Connectify Developer’s Kit (CDK)** includes built-in logging tools and supports integration with Python’s standard `logging` module for consistent, configurable output.

***

#### 🪵 Enabling Basic Logging

You can enable logging with just a few lines of code:

<pre class="language-python"><code class="lang-python"><strong>python
</strong><strong>
</strong><strong>import logging
</strong>from connectify_sdk import ConnectifyClient

# Configure logging
logging.basicConfig(level=logging.INFO)

client = ConnectifyClient(api_key="your_api_key_here")
devices = client.get_devices()
</code></pre>

**What it does:**\
Displays SDK events such as request initiation, response status, and warnings directly in your console.

***

#### 🧠 Using Advanced Debug Mode

Enable **debug mode** for detailed insights during development:

```python
python

client = ConnectifyClient(api_key="your_api_key_here", debug=True)
```

When `debug=True`, the SDK logs additional details like request URLs, payloads, and execution times — useful for tracing issues or optimizing performance.

***

#### 📁 Custom Log Configuration

You can redirect logs to a file instead of printing them to the console:

```python
python

import logging

logging.basicConfig(
    filename="connectify_sdk.log",
    level=logging.DEBUG,
    format="%(asctime)s - %(levelname)s - %(message)s"
)
```

**What it does:**\
Saves logs to a file (`connectify_sdk.log`) with timestamps, log levels, and custom formatting — ideal for production environments.

***

#### ⚙️ Example Log Output

```sql
pgsql

2025-11-01 12:35:20 - INFO - Sending GET request to /devices
2025-11-01 12:35:21 - INFO - Received 200 OK
2025-11-01 12:35:21 - DEBUG - Response payload: {"devices": [{"id": "dev_001", "status": "active"}]}
```

***

#### 💡 Best Practices

* Use `INFO` level logs in production for minimal noise.
* Enable `DEBUG` only in development or testing.
* Rotate log files periodically to avoid large storage usage.
* Sanitize logs — never record API keys or tokens.

***

✅ **You’re ready to debug like a pro!**\
With proper logging in place, you can easily monitor SDK behavior, diagnose issues, and maintain stable integrations.

***

#### 📚 **Next Steps**

👉 [☕ Java SDK](broken-reference)
