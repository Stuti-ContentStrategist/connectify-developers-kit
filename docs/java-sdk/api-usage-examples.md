# 💬 API Usage Examples

Once your SDK is initialized, you can start making API calls to interact with Connectify’s services.

The examples below show how to perform some common operations — such as retrieving devices, triggering events, and handling responses.

***

#### 📥 Fetch All Devices

```java
java

import com.connectify.sdk.ConnectifyClient;
import com.connectify.sdk.models.Device;

import java.util.List;

public class FetchDevices {
    public static void main(String[] args) {
        ConnectifyClient client = new ConnectifyClient.Builder()
            .setApiKey(System.getenv("CONNECTIFY_API_KEY"))
            .setApiSecret(System.getenv("CONNECTIFY_API_SECRET"))
            .build();

        List<Device> devices = client.devices().getAll();

        for (Device device : devices) {
            System.out.println("Device Name: " + device.getName());
        }
    }
}
```

***

#### 🚀 Trigger an Event

```java
java

import com.connectify.sdk.models.Event;

Event event = new Event("device_update", "Device status changed");
client.events().trigger(event);
System.out.println("Event triggered successfully!");
```

***

#### 📤 Send Data to the API

```java
java

Map<String, Object> payload = new HashMap<>();
payload.put("temperature", 22.5);
payload.put("humidity", 65);

client.data().send("sensor_001", payload);
System.out.println("Sensor data sent successfully!");
```

***

#### 💡 Tip

You can enable detailed logging by configuring the SDK’s debug mode:

```java
java

client.enableDebug(true);
```

This helps track API requests and responses during development.

***

#### 📚 Next Step

👉 [🚫 **Common Exceptions**](common-exceptions.md)
