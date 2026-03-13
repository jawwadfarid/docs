---
description: >-
  Connect your own domain to your CodeWords app. Tell Cody the domain you want,
  add one DNS record at your provider, and your app is live at your custom
  address. SSL is automatic, no code changes needed
icon: lines-leaning
---

# Custom Domain

When your app is live on CodeWords, it gets a `*.codewords.run` URL by default. If you want to use your own domain instead — like `app.yourcompany.com` , you can connect it in a few steps.

### How it works

CodeWords hosts your app and gives it a default address at `yourapp.codewords.run`. When you connect a custom domain, your app becomes accessible at both addresses — the CodeWords URL stays active alongside your custom one. SSL certificates (the padlock in the browser) are provisioned automatically once your domain is connected.

### What you need

Before you can connect a custom domain, you'll need:

* **A live app** — your app must already be deployed and working at its `*.codewords.run` address
* **A domain you own** — either a full domain (e.g. `mycompany.com`) or a subdomain (e.g. `app.mycompany.com`)
* **Access to your domain provider** — this is where you bought or manage the domain (e.g. GoDaddy, Cloudflare, Namecheap). You'll need to add a DNS record there

{% hint style="info" %}
**Not sure where you manage your domain?** Search your email for "domain registration" or "domain renewal" , that'll usually point you to the right place.
{% endhint %}

### Connecting your domain



{% stepper %}
{% step %}
**Tell Cody you want to use a custom domain**

In the chat, just say something like:

* "I want to use my own domain"
* "Connect my domain to this app"
* "Can I use app.mycompany.com?"
{% endstep %}

{% step %}
**Tell Cody you want to use a custom domain**

Cody will ask which domain you'd like to use.
{% endstep %}

{% step %}
**Share your domain with Cody**

Tell Cody the exact domain, for example: `app.mycompany.com` or `mycompany.com`.

Cody will respond with a DNS record you need to add. It looks like this:

| Type    | Name  | Value                  |
| ------- | ----- | ---------------------- |
| `CNAME` | `app` | `cname.vercel-dns.com` |

For root domains (like `mycompany.com`) the record type will be an**A record**instead — Cody will tell you exactly what to add.
{% endstep %}

{% step %}
**Add the DNS record at your domain provider**

Log in to your domain provider and add the record Cody gave you. It's usually under a section called **DNS**, **DNS Settings**, or **DNS Records**.

This is a one-time setup — you won't need to do it again.
{% endstep %}

{% step %}
**Come back to Cody and confirm**

Once you've added the DNS record, tell Cody: _"I've added the DNS record"_ or _"Done, can you check?"_

Cody will verify the connection. If everything is set up:

{% hint style="success" %}
"Your domain is live! Your app is now accessible at `https://app.mycompany.com`"
{% endhint %}

{% hint style="info" %}
**DNS changes can take time.** Usually 1–10 minutes, but in rare cases up to 48 hours depending on your domain provider. If Cody says it's not working yet, wait a bit and say _"Can you check my domain again?"_
{% endhint %}
{% endstep %}
{% endstepper %}

### Domain verification

In some cases, Cody may ask you to verify ownership of your domain before connecting it. This happens when the domain was previously linked to another project.

If this comes up, Cody will give you a **TXT record** to add at your domain provider first. After you confirm it's added, Cody will verify ownership and then proceed with the normal setup.

You don't need to do anything extra — Cody will walk you through it.\\

### Removing a custom domain

If you want to disconnect your custom domain, just tell Cody:

* "Remove my custom domain"
* "Disconnect app.mycompany.com"

Cody will remove the custom domain. Your app stays available at its `*.codewords.run` address.
