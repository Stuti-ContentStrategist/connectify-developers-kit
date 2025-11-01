# 🔑 OAuth 2.0 Setup

The **Connectify Developer’s Kit (CDK)** uses **OAuth 2.0** to provide secure, token-based access to its APIs. This ensures that only authorized applications can interact with your Connectify account and resources.

***

#### 🧭 Step 1: Register Your Application

Before using OAuth 2.0, register your app in the **Connectify Developer Dashboard**:

1. Go to **Developer Settings → OAuth Apps**.
2. Click **Create New Application**.
3. Enter your app name, redirect URL, and permissions scope.
4. Copy your **Client ID** and **Client Secret** — you’ll need them for initialization.

***

#### 🔧 Step 2: Configure OAuth Credentials

Set your credentials as environment variables or in a secure configuration file.

```bash
bash

CONNECTIFY_CLIENT_ID=your_client_id_here
CONNECTIFY_CLIENT_SECRET=your_client_secret_here
CONNECTIFY_REDIRECT_URI=https://yourapp.com/callback
CONNECTIFY_SCOPE=read,write
```

💡 **Tip:** Always use HTTPS for redirect URIs to prevent interception.

***

#### ⚙️ Step 3: Request Authorization Code

**Python:**

```python
python

from connectify import ConnectifyOAuth

oauth = ConnectifyOAuth(
    client_id=os.getenv("CONNECTIFY_CLIENT_ID"),
    redirect_uri=os.getenv("CONNECTIFY_REDIRECT_URI"),
    scope=os.getenv("CONNECTIFY_SCOPE")
)

auth_url = oauth.get_authorization_url()
print(f"Authorize your app by visiting: {auth_url}")
```

**Java:**

<pre class="language-java"><code class="lang-java"><strong>java
</strong><strong>
</strong><strong>ConnectifyOAuth oauth = new ConnectifyOAuth.Builder()
</strong>    .setClientId(System.getenv("CONNECTIFY_CLIENT_ID"))
    .setRedirectUri(System.getenv("CONNECTIFY_REDIRECT_URI"))
    .setScope(System.getenv("CONNECTIFY_SCOPE"))
    .build();

System.out.println("Authorize your app by visiting: " + oauth.getAuthorizationUrl());
</code></pre>

**JavaScript:**

```javascript
javascript

import { ConnectifyOAuth } from "connectify-sdk";

const oauth = new ConnectifyOAuth({
  clientId: process.env.CONNECTIFY_CLIENT_ID,
  redirectUri: process.env.CONNECTIFY_REDIRECT_URI,
  scope: process.env.CONNECTIFY_SCOPE,
});

console.log("Authorize your app by visiting:", oauth.getAuthorizationUrl());
```

***

#### 🔄 Step 4: Exchange Code for Access Token

Once the user authorizes your app, Connectify redirects to your callback URL with an authorization code.\
Use that code to obtain an access token:

**Python:**

```python
python

token = oauth.exchange_code_for_token(auth_code)
print("Access Token:", token)
```

**JavaScript:**

<pre class="language-javascript"><code class="lang-javascript"><strong>javascript
</strong><strong>
</strong><strong>const token = await oauth.exchangeCodeForToken(authCode);
</strong>console.log("Access Token:", token);
</code></pre>

***

#### 🧠 Step 5: Store and Use Tokens Securely

* Save tokens in an encrypted storage or secure database.
* Never expose access tokens in client-side code.
* Use refresh tokens to renew access automatically (covered in the next section).

***

#### ✅ Summary

You’ve now set up OAuth 2.0 authentication for your Connectify SDK integration.\
Your app can securely obtain and use access tokens to interact with Connectify’s APIs on behalf of users.

📚 **Next Step:** [Token Management](token-management.md)
