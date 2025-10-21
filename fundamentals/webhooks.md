---
description: >-
  CodeWords Webhooks are HTTP endpoints that allow external systems to send data
  directly to your CodeWords workflows or Agents.
---

# Webhooks

### Get Started with Webhooks

You can use **Cody** to create and manage **webhooks** that let CodeWords connect with other apps and services.\
A webhook works like a **trigger** — whenever something happens in another app (like a form is submitted, a file is uploaded, or data changes), it can automatically **start a CodeWords workflow**.

Webhooks are useful when you want your workflow to **react to new data instantly** — for example, when a CRM update or external API call should launch an automation.\
They can also **send data back** once the workflow is finished, making them great for building **API-style automations** that process data and return results in real time.

### **Authentication**

* No CodeWords API key required
* The webhook URL itself serves as authentication\
  Each webhook has a unique, hard-to-guess URL that acts as a secure access point.\
  Keep this URL private — anyone with the link can send data to your workflow.

### **Technical Details**

* Always deployed with `app="codewords"` and `trigger="webhook"` .
* Generates a unique CodeWords webhook URL.
* External systems POST JSON data directly to that URL.
* Designed to receive data from external systems and send event notifications as POST requests with a JSON payload.

### HTTP Method

CodeWords currently supports only POST [HTTP Request Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods)

{% code title="Example of anCodeWords Webhook URL" overflow="wrap" %}
```
https://runtime.codewords.ai/webhook/pipedream/webhook/cmcdms29y00003o1ydhuu8jw5/gmail_to_salesforce_automation_webhook
```
{% endcode %}

### Path

This contains a randomly generated webhook URL path, to avoid conflicts with other webhook urls on the CodeWords ecosystem.

{% code title="CodeWordsWebhook structure breakdown" overflow="wrap" %}
```
https://runtime.codewords.ai/webhook/pipedream/webhook/{unique_id}/{endpoint_name}
```
{% endcode %}

* **Protocol:** `https://`
* **Base Domain:** `runtime.codewords.ai`
* **Path:** `/webhook/pipedream/webhook/`
* **Unique ID:** `cmcdms29y00003o1ydhuu8jw5` (randomly generated, hard to guess)
* **Endpoint:**  `/Service_webhook`&#x20;

