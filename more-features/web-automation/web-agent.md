---
description: >-
  A CodeWords remote browser automation tool that can perform authentication and
  complex multi-step tasks
icon: computer-classic
---

# Web Agent

### Overview

The Web Agent is your AI-powered assistant for browser automation. Instead of writing complex scripts, you can simply describe your goal in plain language, and the Web Agent figures out how to achieve it by navigating websites, clicking buttons, and collecting the information you need.

Think of it as a virtual assistant that can browse the web and complete tasks for you.

### When to use the Web Agent

1. **Complex research tasks** where you don’t know all the steps

Example: “Find the CEO’s email on the company website — check the About page, Team page, or Contact form.”

2. **Dynamic websites** that change often (e.g. LinkedIn, news sites)
3. **Exploratory automation** that requires decision-making

Example: “Search for product reviews and summarize the top 5 complaints.”

4. **Authenticated websites** behind logins (e.g. LinkedIn profiles, private dashboards)

### **How It Works**

{% stepper %}
{% step %}
#### Describe your goal

Write a few clear, step-by-step instructions to Cody

"Go to the company website, find the about or team page & locate the CEO’s name and email address."
{% endstep %}

{% step %}
#### The Agent executes the task

The Web Agent:

* Reads and understands your instructions
* Navigates the website automatically
* Clicks the right links and buttons
* Extracts the requested information
* Returns results in your chosen format (text, JSON, or Markdown)
{% endstep %}

{% step %}
#### **Watch It Work**

You can watch the Web Agent in real time through a live browser view — perfect for monitoring progress and debugging.
{% endstep %}
{% endstepper %}



<figure><img src="../../.gitbook/assets/web_agent.gif" alt=""><figcaption></figcaption></figure>

FAQ

<details>

<summary>When should I use the Web Agent?</summary>

Use the Web Agent for complex or dynamic web tasks, especially when:

* You don’t know every step ahead of time (e.g., finding a contact on a company site).
* The website changes frequently or loads content dynamically.
* You need to access logged-in or private pages (like LinkedIn or dashboards).

</details>

<details>

<summary>Can I watch the Web Agent in action?</summary>

Yes. You can view a live browser window as the Web Agent performs your task. This makes it easy to monitor progress, verify results, or debug if something doesn’t go as expected.

</details>

<details>

<summary>What types of websites can it handle?</summary>

The Web Agent works on most modern websites, including dynamic JavaScript-based pages and authenticated sites where you’re logged in. For public pages or simple extractions, consider using Firecrawl for faster performance.

</details>

<details>

<summary>Is it safe to use on private or logged-in pages?</summary>

Yes. The Web Agent runs securely within your authenticated browser session and never shares login credentials externally. All activity stays within your private environment.

</details>
