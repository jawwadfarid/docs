# LinkedIn Profile Finder

<a href="https://codewords.agemo.ai/run/linkedin_profile_finder" class="button primary">Use this template</a>

## Overview

This automation finds LinkedIn profiles and pulls current job details for people listed in a Google Sheet. It reads names from your sheet, looks up the matching LinkedIn profile through your browser, and uses AI to extract the person’s current title and company. Then it writes everything back to the same sheet, so your list stays up to date. It runs as a simple API you can trigger, and it uses Google Sheets, a browser extension, and AI working together behind the scenes to save you hours of manual research.

## Description

This automation enriches people data from a Google Sheet by combining sheet rows, browser-based LinkedIn lookups, and AI technology into a clean, updated spreadsheet. It first reads the names that are missing LinkedIn details, then searches for each person’s LinkedIn profile and grabs the best match. In parallel, it uses AI technology to parse the profile content and pull out the current job title and company. After processing each name (with smart limits to avoid overloading your tools), it writes the LinkedIn URL, title, and company back to the sheet to produce an enriched list that’s ready for outreach, recruiting, or research.

## Key Features

**Google Sheets to LinkedIn enrichment**: Reads names from a sheet and fills in LinkedIn URL, title, and company.

**AI-powered parsing**: Uses the Gemini 2.0 Flash model (via CodeWords Runtime) to extract current role and employer from profile content.

**Browser-driven profile discovery**: Searches LinkedIn through a browser extension to find the most likely profile match.

**Safe concurrency**: Looks up multiple names at once with a sensible cap (5 at a time) to stay fast and stable.

**Single endpoint, simple trigger**: Exposes a friendly POST endpoint you can call with a sheet ID and a row limit.

**Write-back to your sheet**: Updates the original Google Sheet so your source of truth stays current.

**Structured logging**: Uses structlog for clear, actionable logs as the automation runs.

**Production-ready FastAPI app**: Runs with FastAPI and Uvicorn for reliable, lightweight execution.

## Instructions

{% stepper %}
{% step %}
Open the automation and connect your accounts: Google Sheets, LinkedIn (if needed), and CodeWords Runtime (URI + API key).
{% endstep %}

{% step %}
Prepare your sheet: Include a “name” column and make sure you have edit access to the sheet you want to enrich.
{% endstep %}

{% step %}
Copy the Google Sheet ID and paste it into the request when starting a run. Optionally set a max rows value if you don’t want to process everything.
{% endstep %}

{% step %}
Hit run to start enrichment. The automation will search LinkedIn, parse profiles with AI, and gather titles and companies.
{% endstep %}

{% step %}
Check your results in the same sheet. You’ll see LinkedIn URLs, job titles, and companies filled in for processed rows.
{% endstep %}

{% step %}
Tweak and repeat as needed: adjust the row limit, fix any ambiguous names in your sheet, and run again to complete your list.
{% endstep %}
{% endstepper %}

## Use Cases

This automation is perfect for sales, marketing, and recruiting teams who maintain people lists in Google Sheets and need quick, reliable LinkedIn details. It’s great for enriching lead lists, preparing for outreach, checking current roles before a campaign, or building a targeted talent pool. If you’re tired of opening tab after tab and copy-pasting titles and companies, this makes the process fast, consistent, and easy.

## Frequently Asked Questions

<details>

<summary><strong>What does this automation actually do?</strong></summary>

It reads names from a Google Sheet, finds the best LinkedIn profile match through your browser, uses AI technology to pull the current job title and company, and writes those details back to your sheet.

</details>

<details>

<summary><strong>What do I need to provide to get started?</strong></summary>

You’ll need your Google Sheet ID, access to that sheet, LinkedIn access in your browser, and your CodeWords Runtime URI and API key for the AI model. If you’re using a browser extension, have its key configured as well.

</details>

<details>

<summary><strong>How does the AI figure out someone’s title and company?</strong></summary>

The automation converts the profile page content to clean text and sends it to the Gemini 2.0 Flash model (via the CodeWords Runtime). The AI identifies the person’s current job title and employer and returns them in a simple format.

</details>

<details>

<summary><strong>Will it update my sheet automatically?</strong></summary>

Yes. After it finds the LinkedIn profile and extracts details, it writes the LinkedIn URL, job title, and company back to the same Google Sheet.

</details>

<details>

<summary><strong>Can I control how many rows it processes?</strong></summary>

Yes. You can set a max\_rows value when you start the run. It defaults to 50 if you don’t specify.

</details>

<details>

<summary><strong>What happens if there are multiple people with the same name?</strong></summary>

The automation picks the best match using the browser search results and AI parsing. If a result looks ambiguous, you can correct the name or add more context in your sheet and run it again.

</details>

<details>

<summary><strong>Is this safe to run at scale?</strong></summary>

It’s designed to be careful. The automation uses concurrency limits (5 at a time) and structured retries where appropriate. Still, it’s smart to process in batches to avoid rate limits or temporary blocks.

</details>

<details>

<summary><strong>Do I have to keep my LinkedIn tab open?</strong></summary>

No, but you do need working browser access (through the extension) so the automation can perform the searches. Staying signed in to LinkedIn can improve result quality and consistency.

</details>

<details>

<summary><strong>Which tools and libraries are used under the hood?</strong></summary>

It runs a FastAPI app on Uvicorn/uvloop, uses the Google Sheets API (googleapiclient), a browser extension for LinkedIn searches, an Async OpenAI client pointed at the CodeWords Runtime to reach the Gemini 2.0 Flash model, and utilities like markdownify, BeautifulSoup, and lxml for clean parsing.

</details>

<details>

<summary><strong>Can I integrate this with other systems?</strong></summary>

Yes. Because it exposes a simple POST endpoint, you can call it from your CRM, a workflow tool, or another CodeWords automation to chain enrichment into your existing processes.

</details>
