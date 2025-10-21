# Using your own API Key

Let's dive into how you can connect your own apps to CodeWords workflows using API keys to build workflows integrated with external apps.

### Getting started with app connections

Here's how you can connect your own apps to CodeWords workflows in a few easy steps:

### Step 1: Getting your app's API key

First, you'll need the API key for the app you want to connect. Think of an API key as a secret handshake that lets CodeWords communicate with your app. Here's what you do:

1. Log in to the app you want to connect&#x20;
2. Find the section where API keys are listed. This is usually under 'Settings' or 'API'.
3. Copy your API key if it exists; if not, generate a new one.

**Pro tip:** Keep it safe — it's like your app's password.

### Step 2: Connect your app to CodeWords

Now, let's link your app to CodeWords:

1. Log in to your CodeWords account.
2. Go to the '[Account- Keys](https://codewords.agemo.ai/account/keys)' section.
3. Click 'Add Variable' to store the API key.
4. Add a unique variable name. E.g. "ASANA\_API\_KEY"
5. Paste your API key and save the variable.
6. Cody, our AI automation assistant, will handle the rest and securely store your connection details.

<figure><img src="../.gitbook/assets/keyvalue.gif" alt=""><figcaption></figcaption></figure>

### Step 3: Build your workflow

With your API key added, you're ready to build a workflow:

1. You can mention to Cody that you want to create the workflow with the app, and you have the API key saved as VARIABLE\_NAME in your environment variables.
2. Cody will reference the documentation of the app and do the integration seamlessly.
3. If the documentation of the api key is not publicly accessible, you would need to copy and paste the markdown or text to Cody.

## Practical tips and what to watch out for

* **Double-check your API key**: Make sure it's correct and that you have the right permissions set in your app.
* **Test your workflows**: Run a test to ensure everything works as expected before going live.
* **Keep your API key secure**: Treat it like a password and never share it publicly.
