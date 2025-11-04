# 🔢 Versioning

Versioning ensures compatibility, stability, and predictability as your SDK evolves.\
By maintaining clear version control practices, developers can confidently integrate updates without breaking existing implementations.

***

#### 🧭 1. Why Versioning Matters

* **Stability:** Prevents unexpected behavior when APIs change.
* **Traceability:** Allows developers to identify which SDK version introduced a feature or fix.
* **Backward Compatibility:** Ensures older clients continue to function as expected.

***

#### 🔢 2. Semantic Versioning (SemVer)

Follow the **Semantic Versioning** standard:

```
plain text

MAJOR.MINOR.PATCH
```

| Part      | Example | Meaning                               |
| --------- | ------- | ------------------------------------- |
| **MAJOR** | `2.0.0` | Incompatible API changes              |
| **MINOR** | `2.1.0` | New features, backward compatible     |
| **PATCH** | `2.1.1` | Bug fixes or performance improvements |

💡 _Tip:_ Always update your documentation and changelog when version numbers change.

***

#### ⚙️ 3. Managing SDK Versions

* **Tag each release** in your repository (e.g., `v2.0.0`).
* Maintain a **CHANGELOG.md** to document updates and fixes.
* Use **branching strategies** like `main` (stable) and `develop` (testing).
* Consider **automated CI/CD pipelines** for building and tagging new releases.

Example Git command:

```bash
bash

git tag -a v2.0.0 -m "Stable release with authentication updates"
git push origin v2.0.0
```

***

#### 🔍 4. Deprecation Policy

Before removing or altering features:

* Mark APIs as **deprecated** in both documentation and code.
* Provide a **grace period** for migration.
* Offer **migration guides** or upgrade scripts.

Example:

```js
javascript

/**
 * @deprecated Use initSessionV2() instead.
 */
function initSession() {
  // existing logic
}
```

***

#### 📦 5. Version Pinning in Projects

Encourage developers to specify exact SDK versions in dependencies to prevent unexpected updates:

**Example (npm):**

```bash
bash

npm install connectify-sdk@2.1.0
```

**Example (Python):**

<pre class="language-bash"><code class="lang-bash"><strong>bash
</strong><strong>
</strong><strong>pip install connectify-sdk==2.1.0
</strong></code></pre>

***

#### 🧩 6. API Versioning

For SDKs interacting with APIs:

* Include version identifiers in API endpoints.
*   Example:

    ```
    plain text

    https://api.connectify.io/v1/users
    https://api.connectify.io/v2/users
    ```
* Deprecate old endpoints gradually, ensuring backward compatibility.

***

#### 📊 7. Recommended Practices

✅ Maintain consistent versioning across SDK and API.\
✅ Use automated tools (like `semantic-release`) to manage releases.\
✅ Communicate major updates via release notes.\
✅ Keep your changelog human-readable and up to date.

#### 📚 Next Steps

👉 [🧰 Testing & Debugging](broken-reference)
