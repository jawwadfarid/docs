# LinkedIn Profile Extractor

<a href="https://codewords.agemo.ai/run/linkedin_profile_extractor" class="button primary">Use this template</a>

## Overview

This automation extracts rich, structured information from a public LinkedIn profile so you don’t have to copy and paste by hand. It visits the main profile and interest tabs through your browser, converts what it finds into clean text, and uses AI to pull out the important details—like personal info, work history, education, and who they follow. It’s built with FastAPI, uses AI technology for the parsing, and logs everything clearly so you can trust what’s happening behind the scenes.

## Description

This automation turns a single LinkedIn profile link into a complete, structured profile by combining the main profile page and its interest tabs into a clean JSON output. It first generates the URLs for the main profile and each interest tab, then loads each page through a browser extension to capture the content. In parallel, it collects those pages and converts the HTML to readable text, while the AI technology processes each page to extract names, headlines, roles, dates, schools, and followed accounts. After processing all pages, it merges everything into a single, consistent data model to produce a comprehensive profile that’s easy to review, store, or send to your CRM.

## Key Features

**Full-profile coverage**: Pulls personal info, work experience, education, and interests from one LinkedIn URL

**Interest tabs support**: Collects Top Voices, Companies, and Schools the person follows for extra context

**Clean structured output**: Returns a well-defined JSON model ready for databases, CRMs, or spreadsheets

**AI-powered parsing**: Uses AI technology to identify and extract key fields from unstructured profile content

**Browser-based capture**: Scrapes pages through a browser extension for reliable page rendering

**Concurrency control**: Fetches multiple pages in parallel while processing with AI sequentially to reduce duplicate requests

**Clear logging**: Structured logs with context for easier troubleshooting and observability

**Simple API endpoint**: One POST request to get a complete LinkedInProfileResponse with status and data

## Instructions

{% stepper %}
{% step %}
Open the automation and connect your CodeWords account so the AI steps can run
{% endstep %}

{% step %}
Add your browser extension key so it can load the LinkedIn pages through your browser
{% endstep %}

{% step %}
Grab a LinkedIn profile URL and paste it into the request body
{% endstep %}

{% step %}
Hit run to start the extraction; the automation will visit the main profile and interest tabs for you
{% endstep %}

{% step %}
Wait a moment while it processes the pages with AI and merges the results
{% endstep %}

{% step %}
Check your results in the response—the structured JSON includes personal info, experience, education, and interests
{% endstep %}
{% endstepper %}

## Use Cases

This automation is perfect for sales, recruiting, and research teams who want a quick, reliable way to turn a LinkedIn profile into clean, structured data. Great for building prospect lists, enriching candidate records, prepping for outreach, or adding context to a CRM without manual copy-paste. If you want a complete snapshot of someone’s background and interests in a format your tools understand, this makes it easy.

## Frequently Asked Questions

<details>

<summary><strong>What do I need to provide to run it?</strong></summary>

Just a LinkedIn profile URL. The automation handles the rest, including loading interest tabs and extracting the key details.

</details>

<details>

<summary><strong>Does it work with private or restricted profiles?</strong></summary>

It can only extract data that your browser can access. If a profile is private or you’re not allowed to view certain sections, those won’t be captured.

</details>

<details>

<summary><strong>Is this safe for my LinkedIn account?</strong></summary>

This automation uses a browser extension to load pages you’re allowed to see. Avoid running it at aggressive speeds and always follow LinkedIn’s terms of service.

</details>

<details>

<summary><strong>What AI model is used?</strong></summary>

It uses gemini-2.5-flash through the CodeWords Runtime and the OpenAI async client for calling the model.

</details>

<details>

<summary><strong>Can I export the results to my CRM or a spreadsheet?</strong></summary>

Yes—because the output is structured JSON, it’s easy to transform into CSV, push to a CRM, or store in a database.

</details>

<details>

<summary><strong>How accurate is the extraction?</strong></summary>

The AI technology does a strong job on common fields like name, headline, roles, dates, and schools. Still, it’s best to spot-check important records and adjust prompts or post-processing if needed.

</details>

<details>

<summary><strong>How fast is it?</strong></summary>

The automation fetches multiple pages in parallel (up to 3 at once) and runs the AI step sequentially to reduce duplicate requests. Speed depends on the network and page complexity.

</details>

<details>

<summary><strong>Can I change the concurrency?</strong></summary>

Yes. The semaphore is set to process 3 URLs concurrently. You can increase or decrease that value based on your rate limits and reliability needs.

</details>

<details>

<summary><strong>What about the interests data?</strong></summary>

It pulls from three interest tabs—Top Voices, Companies, and Schools—so you can see who they follow and what they’re interested in.

</details>

<details>

<summary><strong>How do errors get handled?</strong></summary>

The automation logs each step with structured context using structlog. If a page fails to load or parse, check the logs and retry with a slower pace or ensure your browser access and extension key are set correctly.

</details>
