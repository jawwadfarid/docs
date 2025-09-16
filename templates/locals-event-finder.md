# Locals Event Finder

<a href="https://codewords.agemo.ai/run/generic_event_finder_with_slack_integration" class="button primary">Use this template</a>

## Overview

This automation finds upcoming events for any topic and city, then sends you a clean summary in Slack, and as HTML, you can drop it into a page or email. It uses AI to scan trusted event sites like Eventbrite, Luma, and Meetup, pulls out the important details, and formats everything so you can quickly decide what’s worth attending. It runs through your browser-friendly scraping tool, pulls in AI for accurate extraction, and posts straight to your Slack DM—so you don’t have to juggle tabs or copy‑paste links.

## Description <a href="#description" id="description"></a>

This automation discovers relevant events by combining well-known event sites (Eventbrite, Luma, Meetup) into a structured summary you can view in Slack or as HTML. It first browses multiple sources and collects the visible page content, then uses AI technology to extract event titles, dates, locations, descriptions, and links. In parallel, it prepares a clean Slack message format so results are easy to scan on mobile or desktop. After AI processing, it can send the summary directly to your Slack DM and also returns an HTML version you can reuse, producing a tidy list that saves time and helps you quickly spot the best events to attend or share with your team.

## Key Features <a href="#key-features" id="key-features"></a>

**Multi-source discovery**: Looks across Eventbrite, Luma, and Meetup to find more events, not just one site’s list.&#x20;

**AI-powered extraction**: Uses Gemini 2.5 Flash to pull clean titles, dates, locations, descriptions, and links from messy page content.

**Slack-ready summaries**: Sends a well-formatted message to your DM with emoji, links, and a quick overview.

**Reusable HTML output**: Returns an HTML summary you can paste into docs, internal pages, or newsletters.

**Location-focused results**: Prioritizes events in your chosen city to keep results relevant.

**Graceful handling of blocked pages**: Uses a stealth proxy and falls back across multiple sources if one blocks scraping or shows a CAPTCHA.

## Instructions

{% stepper %}
{% step %}
Open the automation and connect your accounts: add your CodeWords API key and Slack bot token, and paste your Slack user ID.
{% endstep %}

{% step %}
Send your bot a quick DM in Slack first so a DM channel exists (a simple “hi” works).
{% endstep %}

{% step %}
Enter what you want to find: set a topic (like “AI design”) and a location (like “London”).
{% endstep %}

{% step %}
Decide if you want Slack delivery on: keep “send\_to\_slack” true to get the DM summary.
{% endstep %}

{% step %}
Hit run: the automation will browse event sites, use AI to extract event details, and format everything for Slack and HTML.
{% endstep %}

{% step %}
Review results: check your Slack DM for the quick scan, and use the HTML summary in your internal docs or a newsletter.
{% endstep %}
{% endstepper %}

## Use Cases

This automation is perfect for community managers, team leads, recruiters, and anyone who needs a quick, reliable view of relevant events in their city. Great for planning meetups, building an events calendar, sharing training opportunities with a team, or scouting conferences without spending hours searching multiple sites. If you’re curating a newsletter or an internal events page, the HTML output makes it easy to plug in results and publish fast.

## Frequently Asked Questions

<details>

<summary><strong>What sources does this automation check?</strong></summary>

It checks Eventbrite, Luma (location pages and search), and Meetup to broaden coverage and reduce missed events.

</details>

<details>

<summary><strong>How does the AI extraction work?</strong></summary>

It uses AI technology (Gemini 2.5 Flash via the CodeWords runtime) to read the scraped page content and pull out structured fields like title, date, location, description, and URL.

</details>

<details>

<summary><strong>Do I have to use Slack?</strong></summary>

No. You can set send\_to\_slack to false and just use the API response, which includes the events and an HTML summary.

</details>

<details>

<summary><strong>Why do I need to DM the bot first?</strong></summary>

Slack needs an existing DM channel between you and the bot. Sending a quick message opens that channel so the automation can find it and post your summary.

</details>

<details>

<summary><strong>What Slack permissions are required?</strong></summary>

The bot token needs im: read to list DM channels and chat: write to post messages. Make sure the bot is installed in your workspace.

</details>

<details>

<summary><strong>What if a site blocks scraping?</strong></summary>

The automation uses a stealth proxy and tries multiple sources. If one page is blocked or shows a CAPTCHA, it moves on and still returns results when possible.

</details>

<details>

<summary><strong>Can I change the city or topic?</strong></summary>

Yes—both are request fields. The location defaults to London if you don’t provide one.

</details>

<details>

<summary><strong>Is there a limit to how much content it processes?</strong></summary>

The automation truncates very long scraped content (about 20k characters) before AI processing to stay within model limits.

</details>
