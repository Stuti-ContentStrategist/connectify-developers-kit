# 🚫 Handling Exceptions

The **Connectify Developer’s Kit (CDK)** provides structured exception handling to help developers identify, debug, and recover from runtime or API errors gracefully.\
Proper exception handling ensures your applications remain stable, even when the API encounters unexpected issues.

***

#### ⚙️ Common Exceptions

| Exception Type          | Description                                                 | Typical Cause                        |
| ----------------------- | ----------------------------------------------------------- | ------------------------------------ |
| **AuthenticationError** | Raised when the SDK cannot validate credentials.            | Invalid or expired API key/token     |
| **ConnectionError**     | Occurs when the SDK fails to reach the Connectify server.   | Network outage or incorrect endpoint |
| **TimeoutError**        | Triggered when a request exceeds the maximum wait time.     | Slow or unresponsive network         |
| **RateLimitError**      | Returned when too many requests are made in a short period. | API rate limit exceeded              |
| **ServerError**         | Raised for general 5xx-level server errors.                 | Internal Connectify issue            |
| **SDKError**            | A general-purpose exception for all other SDK-level errors. | Misconfiguration, invalid call, etc. |

***

#### 💡 Example: Basic Exception Handling

```python
python

from connectify_sdk import ConnectifyClient, SDKError, AuthenticationError

client = ConnectifyClient(api_key="your_api_key_here")

try:
    devices = client.get_devices()
    print(devices)
except AuthenticationError:
    print("Authentication failed. Please check your API key or token.")
except SDKError as e:
    print(f"An SDK error occurred: {e}")
except Exception as e:
    print(f"Unexpected error: {e}")
```

**What it does:**\
Ensures that all potential errors — from authentication to internal SDK exceptions — are caught and handled cleanly.

***

#### ⚠️ Example: Retrying Failed Requests

You can also add retry logic for transient network or timeout errors:

```python
python

import time
from connectify_sdk import ConnectifyClient, ConnectionError

client = ConnectifyClient(api_key="your_api_key_here")

for attempt in range(3):
    try:
        response = client.get_status()
        print(response)
        break
    except ConnectionError:
        print("Connection failed. Retrying...")
        time.sleep(2)
```

**What it does:**\
Retries the request up to three times before stopping, allowing temporary network issues to resolve automatically.

***

#### 💡 Best Practices

* Always catch specific exception types first.
* Log error details for debugging and support purposes.
* Avoid exposing sensitive information (like tokens or credentials) in error messages.
* Use exponential backoff when retrying API calls to avoid rate limiting.

***

✅ **You’re covered!**\
You now know how to safely manage and debug errors while working with the Python SDK.

***

#### 📚 **Next Page**

👉 [🧾 Logging & Debugging](logging-and-debugging.md)
