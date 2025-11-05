# 🧱 Environment Setup

Before initializing the **Connectify Software Development Kit (SDK)**, you need to set up your local environment properly. This ensures that all SDK components, dependencies, and configurations work seamlessly across different platforms.

#### 🖥️ System Preparation

1. **Install a Supported Programming Language:**
   * 🐍 Python 3.8 or later
   * ☕ Java 11 or later
   * ⚡ Node.js 16 or later
2. **Check Your Network Access:**\
   Ensure outbound HTTPS access is enabled so the SDK can communicate with Connectify’s cloud services.
3.  **Set Environment Variables:**\
    The SDK uses environment variables to store secure credentials and configuration data.&#x20;

    Create a `.env` file in your project root or use your system’s environment manager to add the following:

    ```bash
    bash

    CONNECTIFY_API_KEY=your_api_key_here
    CONNECTIFY_API_SECRET=your_api_secret_here
    CONNECTIFY_ENV=production
    ```

💡 **Tip:** Never commit your `.env` file to public repositories.

#### 🧰 Dependency Installation

Install all required dependencies for your chosen language:

*   **Python:**

    ```bash
    bash

    pip install connectify-sdk
    ```
*   **Java:**

    ```bash
    bash

    mvn clean install
    ```
*   **JavaScript:**

    ```bash
    bash

    npm install connectify-sdk
    ```

#### ✅ Verification

After setup, verify that your SDK is recognized:

*   **Python:**

    ```bash
    bash

    python -m connectify --version
    ```
*   **Java:**

    ```bash
    bash

    java -jar connectify-sdk.jar --version
    ```
*   **JavaScript:**

    ```bash
    bash

    node -e "require('connectify-sdk'); console.log('CDK loaded successfully');"
    ```

If the commands return a valid version number or confirmation message, your environment setup is complete 🎉

***

#### 📚 **Next Page**

👉 [⚡ SDK Initialization](../java-sdk/sdk-initialization.md)\
