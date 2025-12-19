---
description: >-
  Get started by building your first workflow automation on CodeWords through
  prompts.
hidden: true
icon: rocket
---

# Build your first automation

Welcome to CodeWords! This tutorial will guide you through building your first workflow automation.&#x20;

You’ll create a workflow that scrapes content from a web page, summarizes it with AI, and sends the summary to your Gmail inbox.

### Building your first automation: web scraper and Gmail summarizer

#### Step 1: Describe your automation idea

**Goal:** Scrape a web page → summarize content with AI → send summary via Gmail.

**User prompt example:**

> “Build a workflow that scrapes data from a URL and emails the summary to my Gmail.”

**Cody’s planning process:**

1. Cody checks for the available automation templates to see if any are similar.&#x20;
2. Cody confirms whether you've already linked to the necessary app integrations.
3. An automation plan is generated:

* **Web scraping:** Extract main text content from a target URL.
* **AI summarization:** Generate a concise, easy-to-read summary.
* **Email composition:** Create a formatted email with the summary.
* **Gmail delivery:** Send the email directly to the user’s inbox.

Once you've given approval, Cody begins building.

#### Step 2: Cody builds the extraction module

**What Cody builds:**

* Accepts a public URL as input.
* Navigates to the web page and extracts the main text content.
* Ignores ads, navigation, and sidebars for clean data.

**Test Example:**

* Input: `https://www.nationalgeographic.com/science/article/ancient-dna-reveals-woolly-mammoths-final-years`

**Results:**

* Valid URL recognized
* Page scraped successfully
* 1,200 words extracted
* Content relevance

#### Step 3: Add AI summarization and Gmail delivery

**What Cody adds:**

* Processes the extracted text with an AI summarization model.
* Generates a 4-point summary of the article’s key findings.
* Connects securely to Gmail using OAuth authentication.
* Composes and sends an email with the title as the subject and the summary in the body.

**Testing tesults:**

* Summary generated successfully
* Gmail connection verified (`your.email@gmail.com`)
* Email formatted and delivered correctly

#### Step 4: Final workflow test

**Goal:** Validate the full automation end-to-end.

Cody runs the workflow:

* The website is scraped successfully.
* The AI-generated summary is concise and accurate.
* The Gmail message is delivered with correct formatting and source link.

**User confirmation:**

You can tell Cody whether you're happy with the results, or whether there are still adjustments you'd like to make.&#x20;

1. "Yes, it’s exactly what I wanted."
2. "I’d like to make adjustments."

Once confirmed, Cody deploys your automation.

#### Step 5: Deployment and automation URL

Cody provides a unique URL so you can access the run page of your automation:

> `https://codewords.agemo.ai/run/web-summarizer-automation-xyz789`

You can run or modify your automation anytime by clicking `Remix`  &#x20;

#### Step 6: Troubleshooting guide

**Website scraping issues**

* Invalid URL: Ensure the link is public and accessible.
* Blocked content: Some sites prevent scraping. Try a simpler article-based site.
* Empty results: The page might be image- or video-heavy.

**AI summary issues**

* Low quality summary: Use more structured or factual content.
* Adjust prompt: Ask for “3 bullet summary” or “1-paragraph summary.”

**Gmail delivery issues**

* Permission error: Re-authenticate Gmail integration.
* Email missing: Check spam/junk folder and whitelist sender.

### Summary

You’ve successfully built your first end-to-end workflow automation with CodeWords, congratulations!&#x20;

Here's what it does:

* It accepts any public article URL as an input.
* Next, it extracts the core text content automatically through web scraping.
* Then, it generates an AI-powered summary highlighting the key insights.
* Finally, it delivers the summary directly to your Gmail inbox, fully formatted and ready to read.

Your automation now combines real-time web data extraction, AI summarization, and email delivery — all created through natural language in just a few steps.

{% embed url="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FC0KQHHlFG9y1F0pBotb8%2Fuploads%2F6uIsjCxz1BNbwZijPqVN%2Fquickstart_small.mp4?alt=media&token=a68bd407-d46e-41bd-9da0-fce859a2cf61" fullWidth="false" %}
Building Your First Automation: Web Scraper & Gmail Summarizer
{% endembed %}

### FAQ

<details>

<summary>Do I need coding experience to follow this tutorial?</summary>

No. Everything in this guide can be done with plain English prompts. CodeWords automatically builds the logic, connects integrations, and handles deployment behind the scenes.

</details>

<details>

<summary>How long will this take to complete?</summary>

Most users finish in under 10 minutes. The workflow setup is intentionally short: add your URL, let CodeWords summarize the content with AI, and send the result to your inbox.

</details>

<details>

<summary>What kind of web pages work best?</summary>

You can use any publicly accessible, text-based website — like blog posts, articles, or documentation pages. Avoid paywalled or login-protected pages. If you would like to run it on paywalled or login-protected pages you can use our[ Chrome extension](https://docs.codewords.ai/web-automation/chrome-extension) or [Web Agent](https://docs.codewords.ai/web-automation/web-agent) to access these data.

</details>

<details>

<summary>Can I customize what gets summarized or how the email looks?</summary>

Yes. You can adjust the AI prompt (“write a short summary,” “list three key points,” etc.) and change the email recipient, subject, or format in the workflow editor.

</details>

<details>

<summary>What if something doesn’t work as expected?</summary>

Check that your connected apps (Gmail, Web Agent) are authorized and active. Then open the Run Logs inside CodeWords to see detailed errors. The Troubleshooting Guide

</details>

### Next steps

Now that you’ve finished the Quickstart, you can:

* Meet [Cody, the AI Assistant](https://docs.codewords.ai/fundamentals/introduction-to-cody)
* Learn how [Triggers](https://docs.codewords.ai/fundamentals/triggers) work
* Explore [Templates](https://docs.codewords.ai/use-cases/templates)

