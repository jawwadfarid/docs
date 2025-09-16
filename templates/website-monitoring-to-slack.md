# Website Monitoring to Slack

<a href="https://codewords.agemo.ai/run/website_monitoring_to_slack" class="button primary">Use this template</a>

### Overview

This automation keeps an eye on your websites and posts helpful updates to Slack when something changes. It uses AI to spot meaningful edits—like pricing updates, new logos, or feature tweaks—so your team doesn’t have to manually check pages all day. Under the hood, it grabs clean page content and screenshots, compares the latest version to the last snapshot, and sends a friendly summary to a Slack channel. It runs as a lightweight web app you can call whenever you want to (or schedule), and it ties together scraping, change detection, and Slack notifications in one place.

### Description

This automation monitors one or more websites for changes by combining website content, AI technology, and Slack into a simple change report. It first loads each page and extracts clean content and a full-page screenshot, then compares what’s new against the last saved snapshot to find differences. In parallel, it uses AI technology to summarize what changed and how important it is, especially if you ask it to focus on things like pricing or customer logos. After processing those differences, it stores the new snapshot for next time and posts a friendly update to your Slack channel, producing a quick, readable summary that helps your team react faster without constant manual checks.

### Key Features

**Website change tracking**: Monitors any list of URLs for updates and keeps a running snapshot history.

**Smart summaries with AI**: Explains what changed and rates the impact as minor, moderate, or major.

**Focus areas you choose**: Ask it to watch for pricing, logos, feature updates, or anything else you care about.

**Slack notifications**: Sends clean, readable updates right into your chosen Slack channel.

**Clean content extraction**: Uses a website crawler to pull readable page text and a full-page screenshot.

**Git-style diffs**: Generates clear before/after comparisons to pinpoint exactly what moved or changed.

**Managed storage**: Uses Redis to store and retrieve previous snapshots for reliable comparisons.

**Simple web endpoint**: Trigger monitoring through a single POST request to the FastAPI endpoint.

### Instructions

{% stepper %}
{% step %}
Open the automation and connect your CodeWords runtime so it can use AI and managed Redis.
{% endstep %}

{% step %}
Connect Slack by adding your bot token and inviting the bot to the channel where you want updates.
{% endstep %}

{% step %}
Make a list of the URLs you want to watch—start with your pricing page, homepage, or product pages.
{% endstep %}

{% step %}
Optional: Add a short note about what to focus on (like “pricing changes, new customer logos, feature updates”).
{% endstep %}

{% step %}
Send a POST request to the / endpoint with your URLs, focus note (optional), and Slack channel name.
{% endstep %}

{% step %}
Watch Slack for summaries. If you want to expand the list, just rerun with more URLs or change the focus.
{% endstep %}
{% endstepper %}

### Use Cases

This automation is perfect for product teams, marketing, and sales who need to know when key pages change—like pricing, competitor features, or new logos—without manually checking every day. It’s also great for customer success teams tracking updates to docs or terms, and for founders who want a quick pulse on what’s new on their site or competitors’ sites. You get timely, plain‑English updates in Slack so your team can respond quickly.

### Frequently Asked Questions

<details>

<summary><strong>What exactly does this automation monitor?</strong></summary>

It checks the URLs you provide for content changes, captures a snapshot, and compares it to the last version. It then uses AI technology to summarize what changed and how important it might be.

</details>

<details>

<summary><strong>Can it focus on specific things like pricing or new logos?</strong></summary>

Yes. Add a short description (for example, “pricing changes, new customer logos”) and the AI will pay special attention to those areas when summarizing.

</details>

<details>

<summary><strong>How do I get alerts in Slack?</strong></summary>

Provide the Slack channel name in your request. The automation formats a clean summary and posts it directly to that channel using your Slack bot token.

</details>

<details>

<summary><strong>What tools does it use behind the scenes?</strong></summary>

It’s a FastAPI app that uses Firecrawl for scraping and screenshots, Redis for storing snapshots, the CodeWords AI runtime (Gemini) for change analysis, and the Slack SDK to send messages. It can also use ChatGPT via the CodeWords runtime to polish Slack formatting.

</details>

<details>

<summary><strong>How often does it check my sites?</strong></summary>

You control the schedule. Trigger it manually or hook it up to your preferred scheduler or workflow tool to run on a cadence.

</details>

<details>

<summary><strong>Will it post if there are no changes?</strong></summary>

No, notifications are sent when changes are detected or when a page is being tracked for the first time (so you know monitoring is live).

</details>

<details>

<summary><strong>Does it store my page content?</strong></summary>

It stores a snapshot representation in Redis so it can compare the next run to the last one. This enables accurate diffs and smarter summaries.

</details>

<details>

<summary><strong>Can I monitor many URLs at once?</strong></summary>

Yes. Include multiple URLs in the request. The automation will check each one and post Slack updates per site when changes are found.

</details>

<details>

<summary><strong>What if the bot can’t find my channel?</strong></summary>

Make sure the bot is installed in your workspace, invited to the channel, and has permission to read channels and post messages. Use the channel’s name (without #).

</details>
