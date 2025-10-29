---
description: >-
  Get started by building your first automation on CodeWords through natural
  prompts
icon: rocket
---

# Quickstart

In this tutorial, you’ll learn how to automate content extraction and summarization with CodeWords - no code, just natural language. You’ll create a workflow that scrapes content from a web page, summarizes it with AI, and sends the summary to your Gmail inbox.

### Building Your First Automation: Web Scraper & Gmail Summarizer

#### Step 1: Plan Your Automation

**Goal:** Scrape a web page → summarize content with AI → send summary via Gmail.

**User Input Example:**

> “Build a workflow that scrapes data from a URL and emails the summary to my Gmail.”

**Cody’s Planning Process:**

* **Template Search:** Checks from the available automation templates.
* **Integration verification:** Confirms access to necessary app integrations.
* **Automation Plan Generated:**
  * **Web scraping:** Extract main text content from a target URL.
  * **AI summarization:** Generate a concise, easy-to-read summary.
  * **Email composition:** Create a formatted email with the summary.
  * **Gmail delivery:** Send the email directly to the user’s inbox.

Once approved, Cody begins building.

#### Step 2: Cody builds the extraction module

**What Cody Builds:**

* Accepts a **public URL** as input.
* Navigates to the web page and **extracts the main text content**.
* Ignores ads, navigation, and sidebars for clean data.

**Test Example:**

* **Input:** `https://www.nationalgeographic.com/science/article/ancient-dna-reveals-woolly-mammoths-final-years`

**Results:**

* Valid URL recognized
* Page scraped successfully
* 1,200 words extracted
* Content relevance

#### **Step 3: Add AI Summarization and Gmail Delivery**

**What Cody Adds:**

* Processes the extracted text with an **AI summarization model**.
* Generates a **4-point summary** of the article’s key findings.
* Connects securely to **Gmail** using OAuth authentication.
* Composes and sends an email with the title as the subject and the summary in the body.

**Testing Results:**

* Summary generated successfully
* Gmail connection verified (`your.email@gmail.com`)
* Email formatted and delivered correctly

#### Step 4: Final Workflow Test

**Goal:** Validate the full automation end-to-end.

Cody runs the workflow:

* The website is scraped successfully.
* The AI-generated summary is concise and accurate.
* The Gmail message is delivered with correct formatting and source link.

**User Confirmation:**

1. Yes, it’s exactly what I wanted.
2. I’d like to make adjustments.

Once confirmed, Cody deploys your automation.

#### Step 5: Deployment and Automation URL

Cody provides a unique execution URL:

> `https://codewords.agemo.ai/run/web-summarizer-automation-xyz789`

You can run or modify your automation anytime.

#### Step 6: Troubleshooting Guide

**Website Scraping Issues**

* **Invalid URL:** Ensure the link is public and accessible.
* **Blocked content:** Some sites prevent scraping. Try a simpler article-based site.
* **Empty results:** The page might be image- or video-heavy.

**AI Summary Issues**

* **Low quality summary:** Use more structured or factual content.
* **Adjust prompt:** Ask for “3 bullet summary” or “1-paragraph summary.”

**Gmail Delivery Issues**

* **Permission error:** Re-authenticate Gmail integration.
* **Email missing:** Check spam/junk folder and whitelist sender.

### Summary

You’ve successfully built your first end-to-end CodeWords automation. It:

* **Accepts any public article URL** as input.
* **Extracts the core text content** automatically using web scraping.
* **Generates an AI-powered summary** highlighting the key insights.
* **Delivers the summary directly to your Gmail inbox**, fully formatted and ready to read.

Your automation now combines real-time web data extraction, AI summarization, and email delivery — all created through natural language in just a few steps.

{% embed url="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FC0KQHHlFG9y1F0pBotb8%2Fuploads%2F6uIsjCxz1BNbwZijPqVN%2Fquickstart_small.mp4?alt=media&token=a68bd407-d46e-41bd-9da0-fce859a2cf61" fullWidth="false" %}
Building Your First Automation: Web Scraper & Gmail Summarizer
{% endembed %}

