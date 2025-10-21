---
description: >-
  Turn any public LinkedIn post into a structured contact list. This workflow
  scrapes profiles from people who reacted to a post, then enriches those
  profiles and saves everything to a Google Sheet.
icon: linkedin
coverY: 0
---

# LinkedIn Post Scraping and Enrichment

## Who is this for?

<table data-view="cards"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><h4>Marketers</h4></td><td>Capture leads or audience data from posts that sparked interest. Use it to retarget, segment, or personalize campaigns.</td></tr><tr><td><h4>Founders</h4></td><td>See exactly who’s engaging with your thought leadership—or that of your competitors. Use it to identify potential hires, investors, or partners.</td></tr><tr><td><h4>Sales &#x26; BD Teams</h4></td><td>Mine high-intent leads from relevant industry posts. Reach out while your brand (or topic) is still top-of-mind.</td></tr><tr><td><h4>Recruiters</h4></td><td>Engage people who are reacting to job posts, industry updates, or team announcements—often a sign of interest or availability.</td></tr><tr><td><h4>Community &#x26; Events Managers</h4></td><td>See who’s active around your brand’s posts or related content. Perfect for follow-ups, invites, or engagement loops.</td></tr><tr><td><h4>Analysts &#x26; Researchers</h4></td><td>Export and analyze audiences engaging with specific topics. Spot trends, segment personas, or map networks.</td></tr></tbody></table>

## Set up guide

{% stepper %}
{% step %}
### Log in to [CodeWords](https://codewords.agemo.ai/) and go to the [LinkedIn Post Scraping and Enrichment](https://codewords.agemo.ai/run/scrape_and_enrich_linkedin_post_to_google_sheets) workflow
{% endstep %}

{% step %}
### Complete your setup (it takes four clicks)

Connect to Google Sheets and download the CodeWords Chrome Extension if you haven't already.

<figure><img src="../../.gitbook/assets/Screenshot 2025-05-28 at 16.35.26.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Complete the Input section

* **Paste the LinkedIn post URL** into the **Post URL** input field.
* _(Optional)_ Add any specific enrichment instructions\
  Example: “Include years of experience and current location.”
* **Choose what info you want to extract** (e.g., name, company, job title, etc.).
{% endstep %}

{% step %}
### Click Run

The workflow will scrape and enrich up to 250 profiles from the post.&#x20;
{% endstep %}

{% step %}
### View Results in your Google Sheet

We'll create a Google Sheet for you with the enriched details (the link will be in the output). You’ll get a clean table with LinkedIn URLs, names, job titles, companies, and any extra info you selected.\
\
It usually takes a few minutes, depending on the number of reactions to the post. For example, if there are 20 reactions, it can take up to 3 minutes; if 250 reactions, up to 15 minutes. The good news is that you can just leave the tab and come back in a few minutes to check the enriched data. You'll also receive an email confirmation when it's complete.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
If you encounter any issues, please reach out to us at support@agemo.ai, or if you're a beta user, get in touch with one of our team members on Slack.
{% endhint %}

## FAQs

<details>

<summary>How is this different from tools like PhantomBuster? </summary>

This workflow is easier to use, more flexible, and much more affordable.&#x20;

* **No setup or coding required.** Just paste a URL and run.
* **Customizable**. You can specify what data to extract in plain English.
* **Lower cost**. Runs typically cost **under $1**, compared to PhantomBuster’s significantly higher pricing.
* **Everything stays in your browser.** None of your data is being uploaded to a remote server.

</details>

<details>

<summary>Is this compliant with LinkedIn’s policies?</summary>

Yes. The workflow scrapes publicly available data from non-authenticated LinkedIn views, staying compliant with LinkedIn’s Terms of Service.

</details>

<details>

<summary>Will people know I viewed their profile?</summary>

That depends on **their privacy settings** and whether you have LinkedIn open in an active browser window. Some users may see a profile view if their settings show all visitors. If you're concerned, we recommend using LinkedIn in private or logged-out mode.

</details>

<details>

<summary>How many profiles can it scrape from one post?</summary>

Up to **250 profiles per post** for now. We're working on increasing that limit soon. This cap is in place to stay within LinkedIn usage boundaries and ensure compliance with their ToS.

</details>

<details>

<summary>Can I use this on posts I didn’t publish myself?</summary>

Yes—any **public** LinkedIn post can be scraped, regardless of who posted it.

</details>

<details>

<summary>Can I choose what data gets extracted?</summary>

Absolutely. You can check off the standard fields you want (e.g., job title, company) and also add free-text instructions for custom enrichment.

</details>

<details>

<summary>What if I get an error or it's returning false results?</summary>

If you notice something off, just let us know via the chat widget on CodeWords, at support@agemo.ai, or on Slack if you're in our Beta group. We’re constantly improving our workflows.

</details>

<details>

<summary>I like the workflow but want to tweak something (like the output format or inputs). Is that possible?</summary>

Yes! Just reach out via the chat widget on CodeWords and type in the variation you'd like. Plus, we're rolling out an edit feature soon, so you'll be able to customize workflows on your own with just a few clicks or a message.

</details>
