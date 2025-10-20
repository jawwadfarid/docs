---
description: >-
  HTTP endpoints that allow external systems to send data directly to your
  CodeWords workflows or Agents.
---

# Webhooks

Custom webhooks are **generic HTTP endpoints** that you can deploy and configure yourself. They can **receive data from any external system** capable of sending HTTP requests. These endpoints are **platform-agnostic** and completely **user-controlled**.

**Authentication:**

* No CodeWords API key required
* **The webhook URL itself acts as authentication**\
  Each endpoint has a unique, hard-to-guess URL that serves as a secure access point. This URL should be kept private and **not shared** with anyone else.

**Technical Details:**

* Always deployed with `app="codewords"` and `trigger="webhook"`
* Returns a **unique CodeWords webhook URL**
* External systems **POST JSON data** directly to that URL
* Designed to **receive data from external systems** and **send event notifications** as POST requests with a JSON payload
