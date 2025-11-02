# 📦 Installation (pip)

### 📦 Installation (pip)

You can install the **Connectify Developer’s Kit (CDK) Python SDK** easily using `pip`, the standard Python package manager.\
Before installation, ensure that your system meets the System Requirements and that you have Python **3.8 or higher** installed.

#### ⚙️ Step 1: Verify Python & pip

Open your terminal or command prompt and run:

```bash
bash

python --version
pip --version
```

If these commands return valid version numbers (e.g., `Python 3.10.5`), you’re ready to proceed.

#### 📥 Step 2: Install the SDK

Install the SDK directly from PyPI:

```bash
bash

pip install connectify-sdk
```

💡 **Tip:** You can also install a specific version if needed:

```bash
bash

pip install connectify-sdk==1.2.0
```

#### 🧱 Step 3: Verify Installation

After installation, check that the SDK was installed successfully:

```bash
bash

pip show connectify-sdk
```

You should see details such as the SDK name, version, and install path.

#### 💡 Optional: Virtual Environment Setup

For clean dependency management, it’s recommended to install the SDK inside a virtual environment.

```bash
bash

python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows
```

Then reinstall the SDK inside your virtual environment:

```bash
bash

pip install connectify-sdk
```

***

✅ **You’re all set!**\
Once installed, you can start importing the SDK into your Python scripts and initializing it.

***

#### 📚 **Next Steps**

👉 [⚙️ SDK Initialization](../java-sdk/sdk-initialization.md)
