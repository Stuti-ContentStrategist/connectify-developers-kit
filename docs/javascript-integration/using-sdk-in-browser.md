# 🌐 Using SDK in Browser

The **Connectify JavaScript SDK** can also be used directly in browser-based applications.

It allows front-end developers to connect with Connectify APIs for displaying data, triggering events, or monitoring real-time updates — all securely through the browser.

***

#### ⚙️ Setup via CDN

You can include the SDK directly in your HTML file using a CDN link:

```html
html

<script src="https://cdn.connectify.com/sdk/connectify-sdk.min.js"></script>
<script>
  const client = new Connectify({
    apiKey: "YOUR_PUBLIC_API_KEY",
    environment: "production",
  });

  client.devices.getAll().then((devices) => {
    console.log("Devices:", devices);
  });
</script>
```

***

#### 📦 Setup via Bundler (Vite, Webpack, etc.)

If you’re using a modern build tool, simply import the SDK as an ES module:

<pre class="language-javascript"><code class="lang-javascript"><strong>javascript
</strong><strong>
</strong><strong>import Connectify from "connectify-sdk";
</strong>
const client = new Connectify({
  apiKey: "YOUR_PUBLIC_API_KEY",
});
</code></pre>

***

#### ⚠️ Security Note

Never expose your **API secret** in browser code.\
For sensitive operations, use a **secure backend proxy** that communicates with Connectify APIs and passes only non-sensitive data to the frontend.

***

#### 💡 Tip

You can combine browser-based event listeners with Connectify’s Webhooks for powerful real-time applications (e.g., dashboards, alerts, or device control panels).

***

#### 📚 Next Step

👉 [🔁 **Async & Promises**](async-and-promises.md)
