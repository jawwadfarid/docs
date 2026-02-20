---
hidden: true
---

# Database connection with Supabase

### Supabase integration for CodeWords

Supabase is not a native CodeWords integration. It’s a **direct API integration**, which means your app connects to Supabase using Supabase client libraries and your own project credentials.

This page explains what you need from the user, how to set up the frontend and backend, how authentication works, and the security rules you must follow.

### What Supabase adds to your CodeWords app

Connecting Supabase gives your app a production-grade backend, including:

* **Database (PostgreSQL)**\
  Store and query your app’s data with full SQL support. Tell Cody what your app needs to remember, and Cody can create the tables and schema that match your data.
* **User authentication**\
  Add secure sign-ups, logins, and access control. Cody can generate authentication flows (like email/password) and connect them to the right pages and permissions in your app.
* **File storage**\
  Upload and serve images and files using Supabase Storage—useful for profile photos, attachments, and user uploads.
* **Real-time updates**\
  Stream changes as data updates. This is useful for chat, live activity feeds, and dashboards that update instantly across users.
* **Edge Fun**\
  Run serverless backend logic on Supabase using JavaScript/TypeScript. Cody can create and deploy functions for tasks like sending emails, handling webhooks, processing payments, or integrating with external APIs.

### Why use CodeWords with Supabase?

Supabase gives you the backend building blocks—database, auth, storage, and server-side logic. CodeWords makes them easy to use without stitching together separate tools.

Instead of designing a UI in one place and setting up the backend somewhere else, you describe what you want in a conversation with Cody. Cody builds the interface and configures the Supabase pieces behind it—tables, permissions, and any supporting logic—so everything works together from the start.

For example, you can say:\
“Add a user feedback form and save responses to the database.”

Cody can generate the form UI and create the Supabase table to store submissions in the same flow. The result is faster iteration, fewer integration steps, and a smoother path from idea to a working app - whether you’re starting from scratch or moving quickly on an existing product.

### Getting Started - Connecting CodeWords with Supabase

{% stepper %}
{% step %}
Register a new Supabase account [**here**](https://app.supabase.com/sign-up) or [**sign in**](https://app.supabase.com/sign-in) if you already have one.

Create an organization if you don't have one.

<figure><img src="../.gitbook/assets/Screenshot 2026-02-20 at 22.08.07.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
Create a **new project** in Supabase.

Click on + New Project, complete the necessary fields, and allow a few minutes for setup.

<figure><img src="../.gitbook/assets/Screenshot 2026-02-20 at 22.10.55.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
Share the the **Supabase Project URL** to Cody

<figure><img src="../.gitbook/assets/Group 1.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
Provide the Cody with the anon public key and the service role secret

Navigate to **Project Settings - API Keys**

<figure><img src="../.gitbook/assets/Screenshot 2026-02-20 at 22.34.02.png" alt=""><figcaption></figcaption></figure>

Copy both the **anon public key** & the **service role secret** and share it with Cody

<figure><img src="../.gitbook/assets/Screenshot 2026-02-20 at 22.28.33.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

Cody will saferty store all your secrets and help you with integrating a database for your needs.
