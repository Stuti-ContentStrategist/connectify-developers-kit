# 🚫 Common Exceptions

While using the **Connectify Java SDK**, you may encounter exceptions related to authentication, connectivity, or API responses. Understanding these exceptions helps you build robust, fault-tolerant applications.

***

#### ⚠️ Authentication Errors

These occur when the SDK cannot validate your API key or secret.

```java
java

try {
    client.devices().getAll();
} catch (AuthenticationException e) {
    System.err.println("Invalid API credentials: " + e.getMessage());
}
```

**Possible Causes:**

* Invalid or expired API keys
* Incorrect environment configuration (e.g., `staging` vs `production`)
* Missing authorization headers

***

#### 🌐 Network Errors

Thrown when the SDK cannot connect to the Connectify API endpoint.

```java
java

try {
    client.data().send("device_001", payload);
} catch (NetworkException e) {
    System.err.println("Network connection failed: " + e.getMessage());
}
```

**Possible Causes:**

* Internet connectivity issues
* Incorrect API base URL
* Firewall restrictions blocking outgoing requests

***

#### 🧱 API Response Errors

Occur when the server returns an error response (e.g., 400, 401, 500).

```java
java

try {
    client.events().trigger(event);
} catch (ApiException e) {
    System.err.println("API call failed: " + e.getStatusCode() + " - " + e.getMessage());
}
```

**Possible Causes:**

* Invalid parameters in API requests
* Unauthorized access attempts
* Internal server errors on the Connectify side

***

#### 💡 Tip

Implement centralized error handling to log, categorize, and alert on exceptions — this ensures quicker debugging and better application stability.

***

#### 📚 Next Page

👉 [🧩 **Configuration File Sample**](configuration-file-sample.md)
