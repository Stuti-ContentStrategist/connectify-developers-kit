# 🧾 Error Logging

Error logging is essential for monitoring SDK behaviors, diagnosing issues, and improving reliability. By implementing structured logging, developers can trace failures, debug more effectively, and maintain system stability.

***

#### 🧭 1. Define Log Levels

Use clear log levels to categorize the importance and impact of events.

| Level     | Purpose                               | Example                                 |
| --------- | ------------------------------------- | --------------------------------------- |
| **DEBUG** | Diagnostic details during development | Function entry/exit, variable values    |
| **INFO**  | General runtime events                | SDK initialized, request started        |
| **WARN**  | Recoverable issues                    | Deprecated API usage, retry triggered   |
| **ERROR** | Failures affecting execution          | Network failure, missing parameter      |
| **FATAL** | Critical system errors                | Authentication failure, data corruption |

💡 _Tip:_ Avoid excessive debug logging in production environments.

***

#### ⚙️ 2. Use Structured Log Formats

Store logs in **JSON** or **key-value** format for easier parsing and integration with monitoring tools.

```json
json

{
  "timestamp": "2025-11-04T10:00:00Z",
  "level": "ERROR",
  "module": "AuthManager",
  "message": "Invalid API key",
  "request_id": "req_12345"
}
```

This makes logs machine-readable and compatible with platforms like **ELK**, **Datadog**, or **CloudWatch**.

***

#### 🧱 3. Centralize Log Storage

Instead of relying solely on local logs:

* Push logs to a centralized server for aggregation.
* Use log streaming tools (e.g., Fluentd, Logstash).
* Enable filtering by tags like `module`, `severity`, or `request_id`.

***

#### 🔄 4. Include Contextual Information

Every log entry should provide context to aid debugging:

* **Request ID** for tracing API calls.
* **User/session ID** to link related events.
* **Error codes** to identify problem sources quickly.

💡 _Tip:_ Use correlation IDs across services to trace distributed requests end-to-end.

***

#### 📊 5. Monitor & Alert

Integrate with alerting systems to detect anomalies in real-time:

* Send alerts for repeated errors or spikes in failure rate.
* Visualize error trends using dashboards.
* Set thresholds for automatic issue escalation.

***

#### ✅ 6. Example: Simple Logger (JavaScript)

```javascript
javascript

function logError(level, message, context = {}) {
  const logEntry = {
    timestamp: new Date().toISOString(),
    level,
    message,
    ...context
  };
  console.log(JSON.stringify(logEntry));
}

// Example usage:
logError("ERROR", "Invalid token", { request_id: "req_9823", module: "Auth" });
```

***

#### 📚 Next Page

👉 [📗 Versioning](versioning.md)
