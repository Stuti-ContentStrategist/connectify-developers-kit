# ⏳ Async Usage

The **Connectify Developer’s Kit (CDK)** supports **asynchronous operations** in Python to help you build faster, non-blocking applications.\
This is especially useful for handling multiple API calls simultaneously — such as fetching device statuses, triggering automations, or logging events in parallel.

***

#### ⚙️ Why Use Async?

* 🚀 Improves performance by handling I/O-bound operations concurrently
* 💡 Prevents your app from freezing during slow network responses
* 🧩 Ideal for real-time dashboards, background jobs, or automation scripts

***

#### 🧱 Example: Async Device Fetch

Here’s how you can use the SDK asynchronously with `asyncio`:

```python
python

import asyncio
from connectify_sdk import AsyncConnectifyClient

async def main():
    client = AsyncConnectifyClient(api_key="your_api_key_here")

    devices = await client.get_devices()
    for device in devices:
        print(f"{device.name} - {device.status}")

# Run the async function
asyncio.run(main())
```

**What it does:**\
Fetches device data asynchronously, allowing your program to perform other tasks while waiting for responses.

***

#### 🔄 Example: Multiple Parallel API Calls

```python
python

import asyncio
from connectify_sdk import AsyncConnectifyClient

async def fetch_data():
    client = AsyncConnectifyClient(api_key="your_api_key_here")

    device_task = client.get_devices()
    user_task = client.get_users()
    automation_task = client.get_automations()

    results = await asyncio.gather(device_task, user_task, automation_task)
    print(results)

asyncio.run(fetch_data())
```

**What it does:**\
Executes multiple API calls in parallel — reducing overall wait time significantly.

***

#### 💡 Tips

* Use `AsyncConnectifyClient` for all async-based operations.
* Wrap your main logic in an `async` function and use `asyncio.run()` to execute it.
* Avoid mixing sync and async calls in the same flow — it can lead to unexpected behavior.

***

✅ **You’re all set!**\
Your SDK can now handle multiple operations concurrently — perfect for responsive apps and real-time systems.

***

#### 📚 **Next Page**

👉 [🚫 Handling Exceptions](handling-exceptions.md)
