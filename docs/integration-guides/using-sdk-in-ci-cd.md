# 🔧 Using SDK in CI/CD

Integrating the **Connectify SDK** into your **CI/CD pipelines** helps you automate builds, tests, and deployments while keeping your device configurations, triggers, and environment variables consistent across all stages of development.

This **section** walks you through how to:

* ⚙️ **Set up the Connectify SDK** for automated testing and deployment
* 🔐 **Securely manage API keys** using CI/CD secrets
* 🧩 **Run SDK-based scripts** in build pipelines
* ✅ **Validate environment consistency** after each deployment

***

#### 🧭 Prerequisites

Before you begin, ensure you have:

* Access to a CI/CD service like **GitHub Actions**, **GitLab CI**, **Jenkins**, or **CircleCI**.
* Valid **Connectify API credentials** stored as environment variables or secrets.
* A working project integrated with the Connectify SDK.

***

#### ⚙️ Setup Steps

**1. Store Secrets Securely**

Add your Connectify credentials as environment variables in your CI/CD service:

```plaintext
plain text

CONNECTIFY_API_KEY=your_api_key
CONNECTIFY_SECRET=your_secret_key
```

**2. Example — GitHub Actions Workflow**

```yaml
yaml

name: CI/CD with Connectify
on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Install dependencies
        run: npm install

      - name: Run Connectify SDK tasks
        env:
          CONNECTIFY_API_KEY: ${{ secrets.CONNECTIFY_API_KEY }}
          CONNECTIFY_SECRET: ${{ secrets.CONNECTIFY_SECRET }}
        run: |
          node scripts/connectify-test.js
```

**3. Sample Script — `connectify-test.js`**

```javascript
javascript

import { Connectify } from "connectify-sdk";

const sdk = new Connectify({
  apiKey: process.env.CONNECTIFY_API_KEY,
  secret: process.env.CONNECTIFY_SECRET,
});

sdk.devices.list().then((devices) => {
  console.log("Connected Devices in CI/CD:", devices);
});
```

***

#### ✅ Verification

* Check your **CI/CD run logs** to confirm SDK initialization.
* Verify that your **environment variables are loaded** correctly.
* Ensure the **Connectify API responds** successfully during each pipeline execution.

***

#### 💡 Best Practices

* Avoid hardcoding any API keys or secrets in your scripts.
* Use **different credentials** for staging and production pipelines.
* Add **retry logic** in case of transient network failures.
* Use **Connectify’s Webhooks** for real-time build notifications.

***

#### 📚 Next Page

👉 [🔗 Integration with External APIs](integration-with-external-apis.md)
