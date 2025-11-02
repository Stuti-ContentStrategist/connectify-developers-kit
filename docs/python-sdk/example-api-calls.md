# 💬 Example API Calls

Once your **Connectify Developer’s Kit (CDK)** is initialized, you can begin making API calls to interact with devices, automations, and other Connectify resources. This section shows simple examples of how to perform basic operations using the Python SDK.

***

#### 🔍 Example 1: Retrieve All Devices

```python
python

from connectify_sdk import ConnectifyClient

client = ConnectifyClient(api_key="your_api_key_here")

devices = client.get_devices()
for device in devices:
    print(f"{device.name} - {device.status}")
```

**What it does:**\
Fetches a list of all devices linked to your Connectify account and prints their names and statuses.

***

#### ⚙️ Example 2: Trigger an Automation

```python
python

automation_id = "auto_12345"
response = client.trigger_automation(automation_id)
print(response)
```

**What it does:**\
Triggers a predefined automation or workflow in your Connectify dashboard.

***

#### 💡 Example 3: Fetch Device Details

```python
python

device_id = "dev_98765"
device = client.get_device(device_id)
print(f"Device: {device.name}, Status: {device.status}")
```

**What it does:**\
Retrieves detailed information about a specific device, including name, type, and last active timestamp.

***

#### 🧾 Example 4: Send Custom Event

```python
python

event = {
    "event_type": "temperature_alert",
    "value": 75,
    "unit": "Celsius"
}

response = client.send_event(event)
print(response)
```

**What it does:**\
Sends a custom event to Connectify for logging, triggering automations, or analytics.

***

#### 🛡️ Error Handling Example

<pre class="language-python"><code class="lang-python"><strong>python
</strong><strong>
</strong><strong>try:
</strong>    client.get_device("invalid_id")
except Exception as e:
    print(f"Error: {e}")
</code></pre>

**What it does:**\
Demonstrates catching and logging SDK or API-level errors gracefully.

***

💡 **Tip:** Use the **sandbox environment** for testing your API calls before deploying them to production.

***

✅ **You’re ready to start building!**\
You’ve now seen how to use the SDK to make real API calls. Next, you’ll learn how to handle these calls asynchronously for faster and non-blocking performance.

***

#### 📚 **Next Steps**

👉 [⏳ Async Usage](async-usage.md)
