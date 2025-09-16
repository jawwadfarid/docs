# Scrape and Enrich LinkedIn Post to Google Sheets

<a href="https://codewords.agemo.ai/run/scrape_and_enrich_linkedin_post_to_google_sheets" class="button primary">Use this template</a>

## Overview

This automation scrapes the people who reacted to or commented on a LinkedIn post, collects their profile links, and spins up a Google Sheet you can share with your team. It uses AI to pull out names and profile URLs from what’s on the page, then kicks off background enrichment to add details like job title, company, email, and more. Everything runs through your browser and lands neatly in Google Sheets so you can review, filter, and take action quickly.

## Description

This automation turns a LinkedIn post’s interactions into a clean, shareable Google Sheet by combining a browser extension for scraping and AI technology for extraction into a structured sheet. It first opens the LinkedIn post and scrolls the reactions list to gather the visible names and profile links, then uses AI to read that content and extract each person’s name and LinkedIn URL. In parallel, it creates a fresh Google Sheet to store the results. After the initial profiles are captured, it starts a background enrichment process that looks up the fields you care about (like company, job title, or email) and writes them into the sheet, producing an up-to-date contact list that’s ready for outreach or follow-up.

## Key Features

**LinkedIn post scraping**: Gathers people who liked or commented on a post directly through your browser.

**AI-powered profile extraction**: Uses AI technology to pull names and LinkedIn profile URLs from the scraped content.

**Automatic Google Sheet creation**: Spins up a new spreadsheet with links and fields ready to fill.

**Background enrichment**: Kicks off enrichment to add job titles, companies, emails, and more while you continue working.

**Customizable fields**: Choose which information to extract, including optional custom details you specify.

**FastAPI endpoint**: A Simple POST endpoint you can call from tools or scripts to run the automation.

**Uses CodeWords runtime + Gemini**: Runs AI extraction via the CodeWords runtime with the gemini-2.0-flash model.

**Structured logging**: Built-in logging with structlog for easy monitoring and troubleshooting.

## Instructions

{% stepper %}
{% step %}
Open the automation and connect your accounts: sign in with Google (for Sheets) and make sure your browser extension is set up for LinkedIn.
{% endstep %}

{% step %}
Paste the LinkedIn post URL you want to process and pick the fields you’d like enriched (you can also add custom info to look for).
{% endstep %}

{% step %}
Hit Run to start. The automation opens the post in your browser, loads everyone who reacted or commented, and captures their info.
{% endstep %}

{% step %}
Give it a minute while AI extracts names and profile URLs, then a new Google Sheet is created for you automatically.
{% endstep %}

{% step %}
Watch enrichment fill in the sheet in the background—job titles, companies, emails, and any extra details you requested.
{% endstep %}

{% step %}
Review and share your sheet. Filter, sort, and use it for outreach or follow-up right away.
{% endstep %}
{% endstepper %}

## Use Cases

This automation is perfect for marketers, recruiters, founders, and sales teams who want to turn engagement on LinkedIn into a targeted outreach list. Whether you’re following up with everyone who reacted to your launch post, building a talent pipeline from a popular discussion, or mapping accounts from a thought leadership thread, this tool gathers the names, links, and key details you need—fast—right in Google Sheets.

## Frequently Asked Questions

<details>

<summary><strong>What exactly does this automation pull from a LinkedIn post?</strong></summary>

It collects the people who reacted to or commented on the post, then uses AI to extract their names and LinkedIn profile URLs. It also starts enrichment to add things like job title, company, email, and more.

</details>

<details>

<summary><strong>How do I choose which fields get enriched?</strong></summary>

In the request, you can pick fields like first name, last name, company, job title, email, location, education, bio, and even a customized outreach message. You can also add your own extra info to look for.

</details>

<details>

<summary><strong>Do I need to keep my browser open?</strong></summary>

The scraping step uses a browser extension to open the post, load reactions, and collect content. Keep the environment that runs the extension available during scraping. After that, enrichment runs in the background.

</details>

<details>

<summary><strong>Where does the data go?</strong></summary>

The automation creates a new Google Sheet and writes the profiles there. As enrichment completes, new columns are filled in automatically.

</details>

<details>

<summary><strong>Which AI model is used?</strong></summary>

It uses the Gemini-2.0-flash model through the CodeWords runtime to parse the scraped content and extract profile info.

</details>

<details>

<summary><strong>Is my Google account required?</strong></summary>

Yes. You need a Google account with permission to create and edit Google Sheets, and the Google Sheets API must be enabled for your account or project.

</details>

<details>

<summary><strong>Will this find emails for everyone?</strong></summary>

Not always. Email lookup can succeed or fail depending on what’s publicly available and your enrichment configuration. You’ll still get names and profile links even if some emails can’t be found.

</details>

<details>

<summary><strong>Can I use this on any LinkedIn post?</strong></summary>

You can use it on posts you can access in your account. If the post or reactions are limited or private, results may be partial.

</details>

<details>

<summary><strong>How long does it take?</strong></summary>

Scraping usually takes a minute or two, depending on the size of the reactions list. Enrichment continues in the background and can take longer as more data is added.

</details>

<details>

<summary><strong>What if I need to add custom details?</strong></summary>

Use the additional information field to describe what you’re looking for (for example: programming languages, years of experience). The AI will try to capture that and add it to the sheet.

</details>
