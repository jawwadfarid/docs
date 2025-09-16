# Competitor Social Summary

<a href="https://codewords.agemo.ai/run/competitor_socials_summary" class="button primary">Use this template</a>

### Overview

This automation finds a competitor’s public social profiles and gives you a quick, plain‑English summary of what they’ve been posting lately. Share a company website, and it hunts for their LinkedIn and Twitter/X links, pulls recent updates, and uses AI to turn that activity into a clear report. It’s a simple way to keep tabs on messaging, product hints, and engagement trends—without manually checking feeds every day.

### Description

This automation summarizes a competitor’s recent social activity by combining their website and public social profiles into a clean, readable report. It first takes a company website you provide and looks through the HTML to spot links to LinkedIn and Twitter/X, then fetches the latest public posts from those profiles. In parallel, it applies AI technology to scan the content for themes like product news, hiring signals, and campaign launches. After processing the posts and highlights, it composes an easy summary with key takeaways, so you get a quick snapshot that helps with competitive research and planning.

### Key Features

**One‑line input**: Paste a competitor’s website and get a summary—no extra setup needed.

**AI summaries**: Uses fast AI technology (Gemini 2.0 Flash) to turn recent posts into a clear, concise report.

**Profile discovery**: Scans the company website’s HTML to find LinkedIn and Twitter/X links automatically.

**Lightweight fetching**: Grabs public posts using simple web requests, keeping things quick and dependable.

**Clear output**: Returns a readable report you can share with your team or paste into docs and slides.

**Fast API endpoint**: Runs as a small FastAPI app, so it’s easy to trigger from other tools and workflows.

**Structured logging**: Uses structured logs for traceability and easier troubleshooting.

**Built for extensibility**: Designed to add more networks later (e.g., YouTube, Instagram) or custom scoring rules.

### Instructions

{% stepper %}
{% step %}
Open the automation and confirm your CodeWords Runtime settings (URI and API key).
{% endstep %}

{% step %}
Grab a competitor’s homepage URL and copy it to your clipboard.
{% endstep %}

{% step %}
Paste the URL into the input and hit run.
{% endstep %}

{% step %}
Wait a moment while the automation finds their LinkedIn and Twitter/X and pulls recent public posts.
{% endstep %}

{% step %}
Review the generated summary—scan the themes, highlights, and any notable trends.
{% endstep %}

{% step %}
Share or export the report to your notes, CRM, or team chat for follow‑up.
{% endstep %}
{% endstepper %}

### Use Cases

This automation is perfect for marketers, product managers, founders, and sales teams who want a quick pulse on competitors without digging through feeds. It’s great for weekly standups, launch monitoring, campaign tracking, or prepping for a sales call—any time you need a fast, reliable read on what a competitor is saying publicly.

### Frequently Asked Questions

<details>

<summary><strong>What do I need to provide?</strong></summary>

Just the competitor’s website URL (like https://example.com). The automation does the rest—finding social links and creating the summary.

</details>

<details>

<summary><strong>Does this use official social APIs?</strong></summary>

No, it relies on public pages and lightweight fetching. If a profile is private or heavily rate‑limited, it may not be included.

</details>

<details>

<summary><strong>Which AI model does it use?</strong></summary>

It calls Gemini 2.0 Flash through the CodeWords Runtime using the OpenAI Python client with a custom base URL.

</details>

<details>

<summary><strong>Can it analyze more networks than LinkedIn and Twitter/X?</strong></summary>

Today, it focuses on those two. It’s designed so you can extend it later to other channels like YouTube or Instagram.

</details>

<details>

<summary><strong>How fresh is the data?</strong></summary>

It pulls the latest publicly available posts at run time. If a profile updates right after you run it, rerun to refresh.

</details>

<details>

<summary><strong>What if the website doesn’t link to social profiles?</strong></summary>

The automation may return a partial report or note that it couldn’t find profiles. You can try another URL (like their newsroom or blog) or add links manually in your process.

</details>

<details>

<summary><strong>Is a login required for LinkedIn or Twitter/X?</strong></summary>

No—this automation only uses publicly visible content. If a profile requires a login, it won’t be analyzed.

</details>

<details>

<summary><strong>Can I run it for multiple competitors at once?</strong></summary>

The API handles one website per request. You can loop over a list in your own script or tool for batch runs.

</details>

<details>

<summary><strong>How is my data handled?</strong></summary>

The automation processes the provided URL and public content to generate a summary. It uses your CodeWords Runtime and API key to call AI and logs standard operational events (no credentials are logged).

</details>

<details>

<summary><strong>Can I change the tone or length of the summary?</strong></summary>

Yes. You can customize the prompt or post‑process the text in your workflow to match your brand voice or length preferences.

</details>
