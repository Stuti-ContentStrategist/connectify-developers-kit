# 🌍 REST Endpoints

The **Connectify REST API** provides structured endpoints to help developers interact programmatically with the Connectify platform.

Each endpoint corresponds to a specific resource — such as devices, users, triggers, or events — and supports standard HTTP methods for performing operations.

#### 🔧 Supported Methods

| Method     | Description                           |
| ---------- | ------------------------------------- |
| **GET**    | Retrieve information or resources     |
| **POST**   | Create new entries or trigger actions |
| **PUT**    | Update existing records               |
| **DELETE** | Remove resources permanently          |

***

#### 📘 Example Endpoint

**GET /devices** — Retrieves all registered devices in your account.

**Request:**

```bash
bash

GET https://api.connectify.io/v1/devices
Authorization: Bearer <your_api_key>
```

**Response:**

```json
json

{
  "devices": [
    {
      "id": "dev123",
      "name": "Smart Plug",
      "status": "active"
    }
  ]
}
```

***

#### ⚙️ Common Endpoint Categories

* **/devices** — Manage and monitor connected devices
* **/users** — Access user information and roles
* **/events** — Fetch or post event data
* **/settings** — Configure SDK or account preferences

💡 **Tip:** Always ensure your API requests are authenticated and your keys are securely stored in environment variables.

***

#### 📚 Next Steps

👉 re[request-and-response-formats.md](request-and-response-formats.md "mention")
