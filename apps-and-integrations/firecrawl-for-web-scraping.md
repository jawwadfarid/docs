---
description: >-
  Learn how to use Firecrawl on CodeWords to scrape websites, extract clean
  text, capture screenshots, and monitor changes automatically — no coding or
  setup required.
icon: scribble
---

# Firecrawl for web scraping

### What is Firecrawl?

Firecrawl is a fast, reliable tool for extracting text, data, and visual content from public web pages. It automatically retrieves clean, structured information from any URL, allowing you to analyze or use that data directly within your workflows.

On CodeWords, Firecrawl comes fully integrated — meaning you can start scraping websites instantly without any additional setup, API keys, or configurations.

### When to use Firecrawl

Firecrawl is perfect for gathering structured information from public web pages quickly and efficiently.

**Best for:**

* Collecting article or blog content
* Tracking website or pricing updates
* Extracting product information from multiple pages
* Researching competitors or market trends
* Gathering content for summaries or analysis

**Avoid using Firecrawl for:**

* Websites that require login access
* Pages with hidden or interactive content (use [Web Agent](https://docs.codewords.ai/web-automation/web-agent) or [Chrome extension](https://docs.codewords.ai/web-automation/chrome-extension) instead)
* Tasks that involve clicking, filling out forms, or multi-step actions

### How Firecrawl works

Firecrawl visits the website you specify, processes the page, and returns the key content in a clean and structured format. You can choose to:

* Extract the **text content** of the page
* Capture a **screenshot** of the page for visual reference
* Combine both for a complete overview

You can then use this information within CodeWords — for example, to summarize it with **Cody**, analyze trends, or connect it with other automations.

### Common use cases

**1. Research and analysis**\
Quickly gather text from news articles, blogs, or reports to create summaries or insights.

**2. Competitor monitoring**\
Automatically check and compare pricing, features, or content updates on competitor sites.

**3. Product data collection**\
Collect information from multiple product pages and compile it into a single, structured view.

**4. Visual monitoring**\
Capture screenshots to track layout or design changes on important web pages.

### FAQs

<details>

<summary>Do I need to install or set up Firecrawl separately?</summary>

No setup is required. Firecrawl is built directly into CodeWords and works automatically within your workflows — no extra configuration or API key is needed.

</details>

<details>

<summary>Can Firecrawl scrape pages that require a login?</summary>

No. Firecrawl only works with publicly accessible pages. For websites that require login access, use the CodeWords Chrome Extension, which can work with your authenticated browser session.

</details>

<details>

<summary>What kind of data can Firecrawl extract?</summary>

Firecrawl can extract readable text, key page content, and full-page screenshots. This makes it ideal for research, monitoring, and analysis tasks.

</details>

<details>

<summary>How fast is Firecrawl?</summary>

Most pages are processed within 2–5 seconds. Larger or more complex sites may take slightly longer, depending on their structure and loading speed.

</details>

<details>

<summary>What if a website blocks scraping?</summary>

Some websites restrict automated access. If you encounter errors or missing data, try using stealth mode, add a short delay, or switch to the Web Agent tool for interactive sites.

</details>

<details>

<summary>Is it legal to scrape any website?</summary>

Only scrape public pages and always follow the website’s terms of service. CodeWords recommends using Firecrawl responsibly for legitimate business or research purposes.

</details>

<details>

<summary>Can I schedule Firecrawl to run automatically?</summary>

Yes. You can set up scheduled workflows in CodeWords to run Firecrawl at specific times — perfect for daily monitoring or report generation.

</details>

<details>

<summary>Does Firecrawl save the data it collects?</summary>

Firecrawl itself doesn’t store your data permanently. You can choose to save the scraped information in your workflow using tools like Redis, Google Sheets, or other connected services.

</details>
