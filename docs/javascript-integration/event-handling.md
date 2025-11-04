# 🎯 Event Handling

The **Connectify JavaScript SDK** provides a simple interface for managing and responding to real-time events. You can subscribe to, trigger, and process events — enabling dynamic and interactive applications that stay in sync with the Connectify platform.

***

#### 🧭 Subscribing to Events

You can listen for specific events using the `on()` method.

<pre class="language-javascript"><code class="lang-javascript"><strong>javascript
</strong><strong>
</strong><strong>client.events.on("device_update", (data) => {
</strong>  console.log("Device updated:", data);
});
</code></pre>

You can also subscribe to multiple events:

```javascript
javascript

client.events.on(["device_online", "device_offline"], (data) => {
  console.log("Device status changed:", data);
});
```

***

#### 🚀 Triggering Events

Events can be triggered programmatically to notify connected services or systems.

```javascript
javascript

client.events.trigger("custom_event", { message: "Hello from Connectify!" });
```

***

#### 🧱 Removing Event Listeners

To stop listening to a particular event:

```javascript
javascript

client.events.off("device_update");
```

Or remove all listeners at once:

```javascript
javascript

client.events.offAll();
```

***

#### 💡 Tip

For browser-based apps, use event listeners to update UI elements in real time — such as status indicators, dashboards, or logs.\
In Node.js, you can use the same pattern for automation scripts or monitoring tasks.

***

#### 📚 Next Step

👉 [🧯 **Troubleshooting**](troubleshooting.md)
