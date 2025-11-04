# 📦 Installation (npm/yarn)

You can install the **Connectify JavaScript SDK** in your project using your preferred package manager — **npm** or **yarn**.

Before installation, ensure that **Node.js 16+** is installed and your environment meets the System Requirements.

***

#### 🧩 Using npm

```bash
bash

npm install connectify-sdk
```

***

#### ⚙️ Using yarn

<pre class="language-bash"><code class="lang-bash"><strong>bash
</strong><strong>
</strong><strong>yarn add connectify-sdk
</strong></code></pre>

***

#### ✅ Verify Installation

Once installed, you can import the SDK into your project:

```javascript
javascript

import Connectify from "connectify-sdk";

console.log("Connectify SDK imported successfully!");
```

If you’re using **CommonJS**, use:

```javascript
javascript

const Connectify = require("connectify-sdk");
```

***

#### 💡 Tip

You can install the SDK globally if you plan to use it in multiple projects:

```bash
bash

npm install -g connectify-sdk
```

However, for most web and Node.js apps, local installation (project-level) is recommended.

***

#### 📚 Next Step

👉 [🧠 **Using SDK in Node.js**](using-sdk-in-node.js.md)
