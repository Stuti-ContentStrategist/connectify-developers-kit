# 🧬 Data Models

The **Data Models** in the **Connectify Developer’s Kit (CDK)** define how information is structured, transmitted, and interpreted between your application and the Connectify Platform.

They serve as blueprints for requests, responses, and entities, ensuring consistency and reliability across all SDK operations.

#### 🧱 Purpose of Data Models

* Standardize the structure of data exchanged between client apps and APIs
* Simplify object handling by mapping JSON responses to predefined classes or objects
* Improve readability and reduce manual parsing errors
* Ensure uniformity across all supported SDK languages (Python, Java, JavaScript)

#### 🧩 Common Model Types

1. **Request Models**\
   Represent the payloads sent from your SDK to Connectify’s API.\
   Example: `DeviceRequest`, `EventTriggerRequest`, `UserActionRequest`
2. **Response Models**\
   Define the data returned from the server after processing a request.\
   Example: `DeviceResponse`, `StatusResponse`, `ErrorResponse`
3. **Entity Models**\
   Represent key objects used in your integrations.\
   Example: `Device`, `Trigger`, `User`, `Session`, `Token`

#### ⚙️ Example (Python)

```python
python

class DeviceResponse:
    def __init__(self, id, name, status, last_active):
        self.id = id
        self.name = name
        self.status = status
        self.last_active = last_active
```

This model helps you access API response data as attributes — instead of navigating raw JSON — making your code cleaner and easier to maintain.

#### 💡 Best Practices

* Keep model definitions minimal and relevant to your use case.
* Use descriptive names for fields and parameters.
* Validate data before serialization or deserialization.
* Reuse existing models to maintain consistency across modules.

***

#### 📚 **Next Pages**

👉 [⚠️ Error Handling](error-handling.md)
