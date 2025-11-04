# 🗑️ Deprecated Features

This page lists SDK features, methods, or parameters that have been **deprecated** in recent versions.

Deprecated items are still functional but will be removed in a future release. Developers are encouraged to migrate to the suggested alternatives.

| **Feature / Method**  | **Deprecated Since** | **Alternative / Replacement** | **Notes**                                                 |
| --------------------- | -------------------- | ----------------------------- | --------------------------------------------------------- |
| `initLegacySession()` | v2.2.0               | `initSession()`               | Unified session initializer with enhanced error handling. |
| `logInfo()`           | v2.1.0               | `sdkLogger.info()`            | Use the new centralized logging module.                   |
| `getUserProfileOld()` | v2.0.0               | `getUserProfile()`            | Updated to support additional user metadata fields.       |

⚠️ **Note:** Deprecated features will continue to function until the next major release but are no longer actively maintained.

#### 📚 Next Pages

👉 [🔮 Upcoming Enhancements](upcoming-enhancements.md)\
