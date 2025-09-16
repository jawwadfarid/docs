# LinkedIn Comment Scraper

<a href="https://codewords.agemo.ai/run/linkedin_comment_scraper" class="button primary">Use this template</a>

## Overview

This automation extracts all comments from a LinkedIn post, cleans and structures them, and delivers the results in a ready-to-use Google Sheet along with a quick preview table. It saves teams hours of manual copy-paste by turning a LinkedIn discussion into an organized dataset of names, profile links, and comment text—ideal for lead follow-up, sentiment review, or campaign analysis. It does the heavy lifting for you using a secure Chrome extension to capture content, OpenAI to parse large/complex threads, and Google Sheets to share results with stakeholders.

### Description

This automation turns any LinkedIn post's comments into a clean, deduplicated Google Sheet by combining a secure Chrome extension for on-page capture, OpenAI for accurate text extraction and structuring, and the Google Sheets API for instant sharing into a centralized spreadsheet. It first uses a Chrome extension (running in your authenticated session) to scrape the complete HTML of the LinkedIn post and comments, then uses OpenAI's large-context processing to extract commenter names, profile URLs, and comment text reliably from noisy HTML.

In parallel, it prepares a new Google Sheet via the Google Sheets API, sets up headers, and ensures access for your account. After validation and deduplication by LinkedIn profile URL, it writes the data to the sheet and generates an HTML-rich markdown preview so you can quickly scan results without opening the sheet. It finishes by returning a direct link to the Google Sheet and a formatted preview that your team can use immediately for outreach, analysis, or reporting.

### Key Features

**One-click LinkedIn capture** : Pulls full comment threads from a given LinkedIn post URL using a secure Chrome extension running in your authenticated session.

**AI-powered parsing** : Uses OpenAI to robustly extract names, profile URLs, and comment text from complex HTML and long threads.

**Automatic deduplication** : Removes duplicates based on LinkedIn profile URL to keep your dataset clean and actionable.

**Instant Google Sheet creation** : Spins up a new Google Sheet via the Google Sheets API and appends all structured comments with timestamps.

**Shareable preview** : Returns an HTML-rich markdown table preview so you can review results at a glance before opening the sheet.

**Scales to long threads** : Handles large posts and many comments using asynchronous processing and large-content parsing.

**Consistent schema** : Outputs standardized columns (Full Name, LinkedIn Profile URL, Comment Text, Timestamp) ready for analysis or export.

**Secure by design** : Uses your authenticated LinkedIn session (via extension) and your Google account permissions; no public posting or scraping credentials are shared.

### Instructions

{% stepper %}
{% step %}
Connect Google Sheets: In the automation's Connections or Settings, grant access to your Google account so it can create and edit spreadsheets.
{% endstep %}

{% step %}
Authorize the Chrome extension: Follow the prompt to enable the extension and ensure you're logged in to LinkedIn in that browser profile.
{% endstep %}

{% step %}
Collect your LinkedIn post URL: Open the post on LinkedIn, copy its URL, and make sure you can see the comments when viewing it.
{% endstep %}

{% step %}
Run the automation: Paste the LinkedIn post URL into the input field and start the run. The automation will scrape, parse with OpenAI, deduplicate, and write to Google Sheets.
{% endstep %}

{% step %}
Review results: Check the returned preview table for a quick scan, then click the provided Google Sheet link to view, filter, and share the full dataset.
{% endstep %}

{% step %}
Export or follow up: Use the sheet for outreach, analysis, or reporting; export to CSV or connect the sheet to BI tools as needed.
{% endstep %}
{% endstepper %}

### Use Case

This automation is ideal for marketing teams, community managers, sales and SDR teams, and analysts who need to quickly turn LinkedIn comment threads into actionable lead lists, sentiment summaries, and campaign insights without manual copy-paste. It helps with event follow-ups, influencer campaign analysis, product feedback mining, and identifying engaged prospects directly from social interactions.

### Frequently Asked Questions

<details>

<summary>What does this automation return?</summary>

It returns a shareable Google Sheet link containing deduplicated commenter data (name, LinkedIn profile URL, comment text) and a formatted preview table for quick review.

</details>

<details>

<summary>Does this automation work on private or restricted posts?</summary>

This automation can extract comments you can view in your authenticated LinkedIn session; if you can't see the comments, it cannot capture them.

</details>

<details>

<summary>How does the Chrome extension keep my account secure?</summary>

This automation uses a Chrome extension running in your signed-in session to read on-page content only for the provided URL and does not post or change anything on your behalf.

</details>

<details>

<summary>Can it handle very long threads with many comments?</summary>

Yes. This automation uses asynchronous processing and large-context OpenAI parsing to handle lengthy threads, though extremely large posts may take longer to process.

</details>

<details>

<summary>What fields are captured?</summary>

By default, this automation extracts full name, LinkedIn profile URL, and comment text. It can be extended to include timestamps or reaction counts if present in the page content.

</details>

<details>

<summary>How does deduplication work?</summary>

This automation deduplicates primarily by LinkedIn profile URL to avoid repeated rows from the same commenter, keeping your dataset clean.

</details>

<details>

<summary>Will it capture replies and nested threads?</summary>

This automation is designed to capture visible comments. Depth of replies captured depends on what the page renders in your session; expanding all comments before running can improve coverage.

</details>

<details>

<summary>Is multilingual content supported?</summary>

Yes. This automation uses OpenAI for text extraction and can handle most languages present in LinkedIn comments.

</details>

<details>

<summary>Can I update the sheet if new comments are added later?</summary>

You can re-run this automation with the same post URL; it will rebuild a fresh sheet or can be configured to append new comments depending on your setup.

</details>
