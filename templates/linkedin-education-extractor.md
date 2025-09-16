# LinkedIn Education Extractor

<a href="https://codewords.agemo.ai/run/linkedin_education_extractor" class="button primary">Use this template</a>

## Overview

This automation pulls a LinkedIn profile through your browser, uses AI to extract all the education details, and gives you a clean, beautiful summary you can share or embed. It solves the hassle of copy-pasting from LinkedIn and trying to make sense of scattered education entries. You get structured data for each school, degree, and date, plus a polished HTML view—powered by a CodeWords browser extension, a lightweight FastAPI app, and AI technology for reliable parsing.

## Description

This automation turns a LinkedIn profile into a structured education history by combining content scraped through your browser with AI technology into a clean HTML summary and JSON data. It first opens the profile via the CodeWords browser extension and pulls readable content, then uses AI to extract the person’s name, general profile info, and the raw education list. In parallel, it cleans the page content to remove layout noise so the AI can focus on the right text. After parsing the raw education section into detailed entries with institutions, degrees, fields of study, and dates, it formats everything into a polished HTML view and returns structured data that’s easy to reuse in CRMs, reports, or websites.

## Key Features

**One-click scraping**: Pulls profile content through the CodeWords browser extension you already use.

**Structured education data**: Breaks education into clear entries (institution, degree, field, dates, notes).

**AI-powered parsing**: Uses GPT-4o to accurately extract and normalize education details.

**Polished HTML output**: Generates a shareable, branded education section you can embed or paste anywhere.

**Error handling that helps**: Friendly messages if the extension isn’t installed, the key is invalid, or the profile isn’t accessible.

**Flexible content fallback**: Accepts markdown, HTML, or text from the extension and adapts automatically.

**Profile context included**: Captures the person’s name and headline so the education section has proper context.

**Privacy-aware access**: Works with profiles you can view in your logged-in browser—no scraping around login walls.

## Instructions

{% stepper %}
{% step %}
Open the automation and make sure your CodeWords browser extension is installed and active.
{% endstep %}

{% step %}
Confirm you’re logged into LinkedIn in your browser so the profile is accessible.
{% endstep %}

{% step %}
Paste the LinkedIn profile URL (e.g., https://www.linkedin.com/in/username/) into the request field.
{% endstep %}

{% step %}
Hit run to start scraping and AI extraction—this usually takes a few seconds.
{% endstep %}

{% step %}
Review the results: you’ll get the person’s name, a structured education history, and a polished HTML block.
{% endstep %}

{% step %}
Copy or embed the HTML, or use the structured JSON to push into your CRM, notes, or website.
{% endstep %}
{% endstepper %}

## Use Cases

This automation is perfect for recruiters, sales teams, career coaches, and research ops who need a clean summary of someone’s education—fast. Great for screening candidates, enriching CRM contacts, prepping interview briefs, creating portfolio pages, or building talent maps without manual copy-paste. If you regularly evaluate LinkedIn profiles and want consistent, reusable education data, this will save time and keep your records tidy.

## Frequently Asked Questions

<details>

<summary><strong>Do I need the browser extension for this to work?</strong></summary>

Yes. This automation relies on the CodeWords browser extension to access the profile content you can view in your logged-in session.

</details>

<details>

<summary><strong>Will this work on private or limited profiles?</strong></summary>

It works on any profile you can view when logged into LinkedIn. If you can’t see it in your browser, the automation can’t access it either.

</details>

<details>

<summary><strong>What happens if the extension isn’t installed or set up?</strong></summary>

You’ll get a helpful error with instructions to install and activate the CodeWords extension and sign in at codewords.agemo.ai.

</details>

<details>

<summary><strong>Is my OpenAI API key required?</strong></summary>

No, even though this automation uses AI technology (gpt-4o) to parse education details, CodeWords' in-built api key will have access to that model.

</details>

<details>

<summary><strong>Does it pull everything from the profile or just education?</strong></summary>

It extracts general profile context (like name) and focuses the detailed output on education. You get both the education entries and a clean HTML summary.

</details>

<details>

<summary><strong>How accurate is the AI extraction?</strong></summary>

Very strong for clearly listed education details. It uses a structured schema to ensure consistent fields and returns empty lists or nulls when info is missing, rather than guessing.

</details>

<details>

<summary><strong>Can I embed the HTML output on my site or share it?</strong></summary>

Yes. The response includes a styled HTML block you can paste into dashboards, notes, or internal tools. It’s designed to look good out of the box.

</details>

<details>

<summary><strong>What if the output is missing a school or date?</strong></summary>

That usually means the information wasn’t visible on the profile. You can re-run after expanding sections on LinkedIn or checking access. The AI won’t invent details it can’t see.

</details>

<details>

<summary><strong>Does this store my data anywhere?</strong></summary>

The automation processes content via the CodeWords runtime and OpenAI. Logging is limited to operational steps (not full profile content). Handle profile data according to your org’s privacy policies.

</details>
