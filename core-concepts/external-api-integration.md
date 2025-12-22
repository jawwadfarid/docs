---
description: >-
  Connect your external apps to CodeWords using API keys for secure, custom
  integrations. Learn how to obtain, manage, and use your API keys to link apps
  seamlessly with your workflows.
hidden: true
icon: link
---

# External API Integration

### Overview

You can connect your external apps directly to CodeWords workflows using your own API keys, enabling secure, customized integrations between CodeWords and the tools you already use.

### 1. Getting your app's API key

An **API key** acts like a secure pass that allows CodeWords to communicate with your app safely.

**To get your API key:**

1. Log in to the app you want to connect.
2. Go to **Settings** → **API** (or a similar section).
3. Copy your existing API key, or generate a new one if needed.

**Pro Tip:**\
Treat your API key like a password, keep it private and never share it publicly.

### **2. Connect Your App to CodeWords**

Now that you have your app’s API key, it’s time to securely link it to CodeWords.

**Here’s how to connect:**

1. Log in to your **CodeWords** account.
2. Navigate to **Account → Keys**.
3. Click **Add Variable** to store your API key securely.
4. Enter a unique variable name (for example: `ASANA_API_KEY`).
5. Paste your API key and click **Save**.

Cody will automatically handle the connection setup and ensure your credentials are securely stored.

<figure><img src="../.gitbook/assets/keyvalue.gif" alt="Saving your external api key on CodeWords Secrets"><figcaption></figcaption></figure>

### **3. Build Your Workflow**

With your API key connected, you’re ready to create your first integrated workflow.

**How to use your API key with Cody:**

* Tell Cody that you’d like to create a workflow using your connected app and that the API key is saved as `VARIABLE_NAME` in your environment variables.
* Cody will automatically reference the app’s documentation and handle the integration setup for you.
* If the API documentation isn’t publicly available, simply paste the relevant Markdown or text into your chat with Cody — it will use that to complete the integration.

### FAQ

<details>

<summary>How do I add my API key to CodeWords?</summary>

Go to Account → Keys → Add Variable, enter a unique variable name (e.g., ASANA\_API\_KEY), paste your key, and click Save. CodeWords stores it securely and uses it when building workflows.

</details>

<details>

<summary>How does Cody use my API key?</summary>

When you ask Cody to build a workflow with your app, it automatically references your saved variable, connects securely, and sets up the integration without exposing your key.

</details>

<details>

<summary>What if my app’s documentation isn’t public?</summary>

Simply paste the relevant API documentation or Markdown into your chat with Cody. It will read and use that information to complete the integration accurately.

</details>

<details>

<summary>Is my API key safe in CodeWords?</summary>

Yes. All keys are encrypted and stored securely within your environment. They are never shared, exposed, or transmitted outside your workspace.

</details>
