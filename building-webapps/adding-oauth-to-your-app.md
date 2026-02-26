# Authentication

### Add Google OAuth to your CodeWords build

Add Google sign-in to your CodeWords app using Supabase Authentication. Users can log in with their Google account instead of creating a password.

### Overview

CodeWords apps use **Supabase** for authentication. Supabase handles the OAuth flow: redirects, token exchange, session management - so your app never deals with raw tokens or sensitive auth logic directly.

Google OAuth can be configured in two ways:

* **Supabase-managed credentials (recommended):** Supabase provides a shared Google OAuth client. No Google Cloud Console setup required.
* **Your own credentials:** You create an OAuth client in your own Google Cloud project and connect it to Supabase. This gives you full control over branding, consent screen, and allowed scopes.

Both options provide the same sign-in experience for your users.

### What you need

Before Cody can set up Google OAuth, you'll need:

1. A **Supabase project** connected to your CodeWords app
2. **(Optional)** A Google Cloud project with OAuth credentials, if you want to use your own

If you don't have a Supabase project yet, you can create one [here](https://supabase.com/).

{% stepper %}
{% step %}
**Connect the Supabase with your app**

Refer to [connecting to Supabase](https://docs.codewords.ai/building-webapps/database-with-supabase) docs for connecting your codewords app.
{% endstep %}

{% step %}
**Enable a Provider for Auth**

Navigate to **Authentication → Sign In/Providers** from the sidebar menu items.

<figure><img src="../.gitbook/assets/Screenshot 2026-02-24 at 15.26.17.png" alt=""><figcaption></figcaption></figure>

Scroll down to see all the **Auth Providers**

<figure><img src="../.gitbook/assets/Screenshot 2026-02-24 at 15.31.11.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
**Enable** **Google as an OAuth Provider**

Enable Google from the list of providers and provide relevant details such as **Client IDs** and **Client Secret** for OAuth.

Add the **callback URL** for **OAuth** in the **Google Cloud Console** under the list of **Redirect URLs** for the **App** you created the **OAuth Client.**

Also ensure that your app in the Google Cloud Console is set to the status of **Published** for enabling OAuth on production.

Refer to [creating an project in google cloud](https://docs.codewords.ai/building-webapps/database-with-supabase) if you are un-sure how to the client credentials.

<figure><img src="../.gitbook/assets/Screenshot 2026-02-24 at 15.34.49.png" alt=""><figcaption></figcaption></figure>

Once all the details have been added, save to enable google for OAuth.
{% endstep %}

{% step %}
**Cody to Implement Google OAuth in the App**

Just let Cody know that you have enabled Google OAuth in Supabase and ask to implement the functionality in the app.
{% endstep %}
{% endstepper %}

### **Creating a Google Cloud project**

Go to [Google Cloud Console](https://console.cloud.google.com/) and create a new project (or use an existing one).

{% stepper %}
{% step %}
**Configure the OAuth consent screen**

Navigate to **APIs & Services → OAuth consent screen**.

* Choose **External** (unless your app is for Google Workspace users only)
* Fill in your app name, support email, and authorized domains
* Add scopes: at minimum, `email` and `profile`
{% endstep %}

{% step %}
**Create OAuth credentials**

Go to **APIs & Services → Credentials → Create Credentials → OAuth client ID**.

* Application type: **Web application**
* Authorized redirect URI: Cody will provide this — it's your Supabase project's callback URL (e.g., `https://<your-project>.supabase.co/auth/v1/callback`)

You'll receive a **Client ID** and **Client Secret**.
{% endstep %}

{% step %}
**Share the Client ID and Client Secret with Cody.**

&#x20;Cody will:

* Store them securely as environment variables
* Set up the sign-in flow in your app
{% endstep %}

{% step %}
&#x20;**Test the flow**

Verify the steps:

* Sign-in button appears
* Redirect to Google works
* User returns signed in
* Consent screen shows your app name and branding
{% endstep %}
{% endstepper %}

#### Session management

* Supabase manages sessions automatically using secure cookies
* Your app checks authentication state using the Supabase client
* Sessions refresh automatically: users stay signed in across visits

#### Adding more OAuth providers

Supabase supports many OAuth providers beyond Google — GitHub, Apple, Microsoft, Discord, and more. Ask Cody to add additional providers to your app.

### Troubleshooting

| Issue                                                                              | Solution                                                                                                |
| ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **Redirect URI mismatch**                                                          | Ensure the redirect URI in Google Cloud Console matches your Supabase callback URL exactly              |
| **Consent screen not showing**                                                     | Check that OAuth consent screen is configured and published in Google Cloud Console                     |
| **User not redirected back**                                                       | Verify the redirect URL is added to both Google Cloud Console and Supabase Auth settings                |
| **"Access blocked" error**                                                         | Your Google Cloud project may need verification. For testing, add test users under OAuth consent screen |
| <p><strong>Auth works in preview</strong></p><p> <strong>but not prod</strong></p> | Ensure the production redirect URI is also added in Google Cloud Console                                |

### Security

* OAuth credentials (Client Secret) are stored server-side only — never exposed to the browser
* Supabase handles token exchange and session management securely
* All communication happens over HTTPS
* Sessions use secure, HTTP-only cookies
* Your app never sees or stores Google passwords

