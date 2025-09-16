# Person Finder

<a href="https://codewords.agemo.ai/run/person_finder" class="button primary">Use this template</a>

### Overview

This automation finds a person’s key social profiles, pulls in what’s publicly available, and uses AI to summarize it all into a clear, human‑readable report. It can start from a LinkedIn URL or just a full name with a bit of context, then searches sites like LinkedIn, Twitter/X, GitHub, and Google Scholar. It scrapes profiles through your browser, analyzes the content with AI, and even attempts a professional email lookup. You get a combined, easy‑to‑scan write‑up you can use for research, outreach, or prep before a meeting.

### Description

This automation discovers and analyzes a person’s online presence by combining public sources into a concise markdown report. It first takes either a LinkedIn URL or a full name with context, then searches across LinkedIn, Twitter/X, GitHub, and Google Scholar to find likely matches. In parallel, it uses AI technology to refine search queries for each site and pick the best profile candidates to review. After scraping the profiles with a browser extension and converting the pages into clean, readable text, it analyzes the content to extract a summary, work history, skills, and recent activity, and can run an email lookup when there’s enough company information. Finally, it cross‑checks details for consistency and generates a combined analysis that’s clear, useful, and ready to share.

### Key Features

**Multi‑platform search**: Finds likely matches on LinkedIn, Twitter/X, GitHub, and Google Scholar.

**Smart query generation**: Uses AI technology to craft better search queries tailored to each platform.

**Best‑match selection**: Chooses the most relevant profiles from search results with confidence scoring.

**Browser‑based scraping**: Captures profile content through a browser extension and converts it to clean markdown.

**AI profile analysis**: Summarizes background, experience, skills, and recent activity into plain language.

**Email lookup**: Attempts to find a professional email when company details are available.

**Cross‑platform consistency**: Compares details across profiles to flag mismatches and increase confidence.

**Keep‑alive streaming**: Long runs stay responsive with gentle heartbeats until the report is ready.

### Instructions

{% stepper %}
{% step %}
Open the automation and connect your CodeWords account by adding your API key and Runtime URI.
{% endstep %}

{% step %}
Add your browser extension key so scraping can run smoothly; connect Hunter.io if you want email lookups.
{% endstep %}

{% step %}
Choose your input: paste a LinkedIn URL, or enter the full name and a little context (company, role, location).
{% endstep %}

{% step %}
Optionally add guidance for the output (for example, “focus on technical skills and recent work”).
{% endstep %}

{% step %}
Hit run and keep the window open; you’ll see small keep‑alive updates while the automation works.
{% endstep %}

{% step %}
Review your combined report, check per‑platform details, and copy or save the results for your workflow.
{% endstep %}
{% endstepper %}

### Use Cases

This automation is perfect for sales and recruiting teams doing prospect research, founders and operators preparing for meetings, and analysts who need a quick, accurate snapshot of someone’s public professional footprint. It’s also great for developer relations and partnerships teams who want a clear view of a person’s work history, skills, and recent activity across platforms—all in one place and ready to share.

### Frequently Asked Questions

<details>

<summary><strong>Do I need a LinkedIn URL to get started?</strong></summary>

No. You can start with a full name plus helpful context like company, role, or location. A LinkedIn URL just speeds up matching.

</details>

<details>

<summary><strong>How long does it take?</strong></summary>

Typical runs finish in about 3–5 minutes. The keep‑alive stream lets you know it’s still working during longer searches.

</details>

<details>

<summary><strong>What sites does it check?</strong></summary>

This automation looks across LinkedIn, Twitter/X, GitHub, and Google Scholar, and can expand with general web search when needed.

</details>

<details>

<summary><strong>How accurate is the matching?</strong></summary>

It uses AI technology to rank candidates and choose the best match based on name, role, company, and other clues. Confidence scores help you gauge reliability.

</details>

<details>

<summary><strong>Can it find emails?</strong></summary>

Yes, when there’s enough company information, it attempts a professional email lookup. Results vary by company and public records availability.

</details>

<details>

<summary><strong>Is scraping allowed?</strong></summary>

It uses a browser extension to capture publicly available pages. Always follow each site’s terms and your organization’s policies.

</details>

<details>

<summary><strong>Can I customize the report?</strong></summary>

Yes. Add simple instructions like “focus on recent publications” or “highlight open‑source work” to tailor the output.

</details>

<details>

<summary><strong>What if there are multiple people with the same name?</strong></summary>

The automation compares details like employer, location, and role to pick the best match. If uncertain, it will reflect lower confidence.

</details>

<details>

<summary><strong>Will it work behind corporate networks?</strong></summary>

Usually, yes, as it uses standard web traffic. If certain sites are blocked, results may be limited.

</details>

<details>

<summary><strong>What happens if something fails mid‑run?</strong></summary>

The keep‑alive stream continues while the automation retries where possible. If a platform can’t be reached, it still returns a combined report with whatever it could analyze.

</details>
