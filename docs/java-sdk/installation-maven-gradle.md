# 📦 Installation (Maven/Gradle)

You can install the **Connectify Java SDK** in your project using your preferred build tool — **Maven** or **Gradle**.

Make sure your environment meets the [System Requirements](../getting-started/system-requirements.md) before proceeding.

***

#### 🧩 Maven Setup

Add the following dependency to your project’s `pom.xml` file:

```xml
xml

<dependency>
  <groupId>com.connectify</groupId>
  <artifactId>connectify-sdk</artifactId>
  <version>1.0.0</version>
</dependency>
```

Then, refresh your Maven project to download the SDK automatically.

***

#### ⚙️ Gradle Setup

For **Gradle (Groovy DSL)** users, add this line to your `build.gradle` file:

```groovy
groovy

implementation 'com.connectify:connectify-sdk:1.0.0'
```

For **Gradle (Kotlin DSL)** users, use:

```kotlin
kotlin

implementation("com.connectify:connectify-sdk:1.0.0")
```

After adding the dependency, run:

```bash
bash

gradle build
```

to sync your project and install the SDK.

***

#### 💡 Tip

If your organization uses an internal artifact repository, ensure that it’s configured in your build file before adding the dependency.

***

#### 📚 Next Page

👉 [⚙️ **SDK Initialization**](sdk-initialization.md)\
