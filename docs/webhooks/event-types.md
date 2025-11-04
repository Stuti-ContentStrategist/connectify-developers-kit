# 🔔 Event Types

**Event Types** define the specific triggers that cause **Connectify** to send webhook notifications to your registered endpoint.

Each event corresponds to a key action or change within your Connectify environment — such as a device going online, a user updating preferences, or an automation being triggered.

Subscribing to relevant events ensures your application receives **only the notifications you need**, improving efficiency and reducing unnecessary processing.

***

#### 📋 Common Event Categories

| Category              | Description                                                 |
| --------------------- | ----------------------------------------------------------- |
| **Device Events**     | Notify when devices connect, disconnect, or change status   |
| **User Events**       | Trigger when user accounts are created, updated, or deleted |
| **Automation Events** | Indicate when automation rules are executed or modified     |
| **System Events**     | Alert on system-wide changes or SDK-level updates           |

***

#### ⚡ Example Event List

| Event Name             | Description                               |
| ---------------------- | ----------------------------------------- |
| `device.online`        | Triggered when a device comes online      |
| `device.offline`       | Triggered when a device disconnects       |
| `user.updated`         | Sent when user data or permissions change |
| `automation.triggered` | Fired when an automation rule is executed |
| `system.maintenance`   | Indicates upcoming scheduled maintenance  |

***

#### 🧠 Example Payload

```json
json

{
  "event": "device.online",
  "data": {
    "device_id": "dev123",
    "status": "online",
    "timestamp": "2025-11-01T09:35:00Z"
  }
}
```

💡 **Tip:** Use event type filters during webhook setup to subscribe only to the events your application actually uses.

***

#### 📚 Next Page

👉 [📦 **Payload Format**](payload-format.md)
