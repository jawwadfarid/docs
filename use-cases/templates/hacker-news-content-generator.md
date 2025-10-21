# Hacker News Content Generator

<a href="https://codewords.agemo.ai/run/hacker_news_content_generator" class="button primary">Use this template</a>

## Overview

This automation turns trending Hacker News posts into ready-to-publish content using AI. It pulls fresh stories, ranks them by relevance to your chosen topics, writes summaries and social posts, generates optional images, and bundles everything into a polished newsletter and an HTML report. If you like, it also saves the content to a Google Drive folder so your team can grab assets in one place. It runs through your browser as a simple API-based workflow, using AI for writing and DALL·E for visuals.

## Description

This automation transforms the Hacker News front page into a content pack by combining live article data, AI technology for writing, and optional image generation into an easy-to-share report. It first scrapes the latest HN stories and parses titles, points, and discussion links, then uses AI to score each article for relevance to your focus topics, write concise summaries, pull out key insights, and draft social posts. In parallel, it can generate DALL·E images from AI prompts and upload everything to a neatly named Google Drive folder. After processing the list, it compiles a professional newsletter and a visual HTML summary with analytics and top picks, delivering publish-ready content that saves time and keeps your audience engaged.

## Key Features

**Automatic HN scraping**: Captures trending titles, links, points, author, and comment counts from the front page.

**AI relevance scoring**: Rates each article 0–1 against your chosen focus topics to surface the best picks.

**Editorial-quality writing**: Generates summaries, key insights, newsletter blurbs, and social posts tailored for a technical audience (OpenAI gpt-5-mini).

**Optional image generation**: Creates on-brand visuals with DALL·E 3 using AI image prompts.

**Google Drive bundling**: Creates a Drive folder, uploads the newsletter and images, and returns shareable links.

**Shareable HTML report**: Produces a clean, styled HTML page with analytics, top articles, and asset links.

**Configurable scope**: Limit to 1–30 articles, set focus topics, and toggle images or Drive uploads.

**Fast, safe execution**: Processes up to three articles at a time for snappy performance and reliability.

## Instructions

{% stepper %}
{% step %}
Open the automation and connect your accounts: CodeWords, OpenAI (for writing and DALL·E), and Google Drive (if you want uploads).
{% endstep %}

{% step %}
Set your options: pick how many articles to process (1–30), add your focus topics, and choose whether to generate images and upload to Drive.
{% endstep %}

{% step %}
Optionally, rename the Drive folder so assets land where your team expects them.
{% endstep %}

{% step %}
Hit run. The automation will scrape Hacker News, analyze articles with AI, draft your newsletter, and (if enabled) generate images.
{% endstep %}

{% step %}
Review your results: read the newsletter text, scan the HTML report, and click through to the HN discussions or original links.
{% endstep %}

{% step %}
If you enabled Drive, open the folder link to find your newsletter file and any generated images ready to share.
{% endstep %}
{% endstepper %}

## Use Cases

This automation is perfect for content marketers, developer relations teams, and tech newsletter authors who want to keep up with Hacker News without spending hours curating. It’s great for creating weekly roundups, social content calendars, or quick executive briefs. If you need consistent, on-brand summaries and visuals tied to your focus areas—like AI, cloud, or security—this saves time and keeps your audience informed.

### Frequently Asked Questions

<details>

<summary><strong>What exactly does this automation pull from Hacker News?</strong></summary>

It scrapes the front page, then parses each story’s title, URL, points, author, comment count, and a link to the HN discussion thread.

</details>

<details>

<summary><strong>How does the AI decide what’s relevant?</strong></summary>

It scores each article from 0–1 against your focus topics using OpenAI’s gpt-5-mini, then sorts by that score so the most relevant items rise to the top.

</details>

<details>

<summary><strong>Can I control how many articles it processes?</strong></summary>

Yes—set max\_articles between 1 and 30. It will scrape the page, then analyze up to your chosen number.

</details>

<details>

<summary><strong>Do I have to generate images?</strong></summary>

Nope. Image creation with DALL·E 3 is optional. Toggle it on or off with the generate\_images setting.

</details>

<details>

<summary><strong>What gets uploaded to Google Drive?</strong></summary>

If you enable uploads, the automation creates a folder, saves the newsletter as a text file, and uploads any generated images. You’ll get the folder link and file IDs back.



</details>

<details>

<summary><strong>Which tools and models are used under the hood?</strong></summary>

Firecrawl handles web scraping, OpenAI GPT-5-mini writes the content, DALL·E 3 generates images via Pipedream OpenAI, and Google Drive uploads run through the Pipedream Google Drive integration. The API is built with FastAPI and orchestrated by the CodeWords client.

</details>

<details>

<summary><strong>How long does it take to run?</strong></summary>

It processes up to three articles at a time for speed. Total time depends on your max\_articles, whether you generate images, and your Drive uploads—usually a couple of minutes.

</details>

<details>

<summary><strong>What does the report include?</strong></summary>

An HTML page with analytics (totals, averages), the top article, content counts, image previews (if made), links to originals and HN discussions, and a Drive section if uploads were enabled.

</details>

<details>

<summary><strong>Can I change the Drive folder name?</strong></summary>

Yes. Set drive\_folder\_name to whatever you like—great for weekly batches or client-specific folders.

</details>

<details>

<summary><strong>What happens if the Drive upload fails?</strong></summary>

The automation still returns your analyzed content, newsletter text, and HTML report. You’ll get a warning in logs, and you can re-run with Drive enabled later.

</details>
