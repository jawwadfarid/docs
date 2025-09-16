# LinkedIn Profile Enricher to CSV

<a href="https://codewords.agemo.ai/run/linkedin_profile_enrichment_to_csv" class="button primary">Use this template</a>

## Overview

This automation enriches a list of LinkedIn profile URLs and turns them into a clean, ready-to-share CSV—complete with names, roles, company info, and a probable work email—using AI, a browser-based fetch, and an email lookup. It pulls profile pages through your browser, extracts useful details with AI, and tries to find a matching business email, then ships everything back as a CSV you can download or plug into your CRM. It's a fast way to go from raw LinkedIn links to usable contact data without manual copying and pasting.

## Description

This automation takes a CSV of LinkedIn profile URLs and turns it into an enriched CSV by combining browser-captured profile pages, AI technology for data extraction, and an email lookup into a single streamlined flow. It first downloads your CSV of LinkedIn URLs and opens each profile through a browser extension to capture the page content cleanly, then converts the page into readable text for processing. In parallel, it uses AI technology to extract structured profile details like first name, last name, title, and company, while also running an email lookup based on the person and the company. After processing each profile, it compiles all the enriched fields and writes them back into a fresh CSV, then uploads the file and returns a handy link so you can download results that are ready to share, import, or sync to your tools.

## Key Features

**Upload a CSV of LinkedIn URLs**: Start with a simple list of profile links you already have.

**Browser-based page capture**: Fetches LinkedIn pages through a browser extension to handle dynamic content reliably.

**AI-powered extraction**: Uses the gemini-2.0-flash model to pull out names, roles, and company details from page content.

**Email lookup**: Tries to find a likely work email using an email finder tool for each profile.

**Parallel processing**: Handles multiple profiles at once for faster turnaround on bigger lists.

**Clean CSV output**: Returns a downloadable CSV with consistent, structured fields for easy import.

**Simple HTTP endpoin**t: Kick off enrichment via a single POST request to the API.

**Hosted upload link**: Automatically uploads the final CSV and provides a link to your enriched results.

## Instructions

{% stepper %}
{% step %}
**Prepare your CSV**: Create a CSV with a single column of LinkedIn profile URLs. Host it somewhere with a shareable link (Google Drive, Dropbox, S3, or a direct file URL).
{% endstep %}

{% step %}
**Open the automation**: Go to your CodeWords workspace and open the LinkedIn Profile Enrichment automation.
{% endstep %}

{% step %}
**Connect accounts**: Add your CodeWords Runtime URL and API key, and set your browser extension key. If you use the built-in email lookup, make sure that's enabled too.
{% endstep %}

{% step %}
**Paste your CSV link**: In the request, set csv\_file\_url to your hosted CSV link. Optionally adjust max\_concurrency to speed things up if needed.
{% endstep %}

{% step %}
**Hit run**: Start the automation. It will fetch profiles, extract key details with AI, and look for work emails.
{% endstep %}

{% step %}
**Check your results**: When it finishes, grab the returned CSV link and download your enriched file for review or import into your CRM or spreadsheet.
{% endstep %}
{% endstepper %}

## Use Case

This automation is perfect for sales, recruiting, and growth teams that have a list of LinkedIn profiles and want a fast, consistent way to enrich them with roles, companies, and likely work emails. It's great for prepping outreach lists, updating a CRM, building a candidate pipeline, or validating prospect data without hours of manual research.

## Frequently Asked Questions

<details>

<summary>What does the input CSV need to look like?</summary>

A simple CSV with one LinkedIn profile URL per row works great. No headers are strictly required, but including a header like URL is helpful.

</details>

<details>

<summary>How does this automation fetch LinkedIn pages?</summary>

It uses a browser extension runner so pages render like they do in a real browser, which improves consistency for dynamic content.

</details>

<details>

<summary>What AI model is used for extraction?</summary>

It uses gemini-2.0-flash through an OpenAI-compatible client to pull out structured fields from page content.

</details>

<details>

<summary>Which fields are extracted?</summary>

By default, it targets first name, last name, and current role details (like title and company). The automation then attempts a work email based on the person and company.

</details>

<details>

<summary>How does the email lookup work?</summary>

It calls an email finder tool (the Hunter email-finder node in CodeWords) using the person's name and company to suggest a likely work email.

</details>

<details>

<summary>How many profiles can it process at once?</summary>

It's designed to run profiles in parallel for speed. You can set max\_concurrency in the request to control how many are processed at the same time.

</details>

<details>

<summary>Where do I get the results?</summary>

When it finishes, the automation uploads the enriched CSV and returns a link you can download.

</details>

<details>

<summary>What if some profiles fail to load or parse?</summary>

That can happen with private or restricted profiles. Those entries will likely be skipped or returned with partial data. You can re-run them later.

</details>

<details>

<summary>Is this allowed under LinkedIn's terms?</summary>

You are responsible for how you use the automation and must follow LinkedIn's terms, plus your organization's data and privacy rules.

</details>

<details>

<summary>Can I customize the output fields?</summary>

Yes—this automation is extensible. You can adjust the extraction prompt or add fields (like location or education) if you want to capture more details.

</details>
