---
description: >-
  Track competitor, partner, or prospect websites—and get instant Slack alerts
  when something meaningful changes (like product updates or pricing shifts). No
  more refreshing pages multiple times a week.
icon: globe-pointer
coverY: 0
layout:
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Website Watcher (Slack Agent)

## Who is this for?

<table data-view="cards"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><h4>Marketers &#x26; Founders</h4></td><td>Stay on top of competitor launches, content, and positioning changes—so you can adapt faster.</td></tr><tr><td><h4>Product Teams</h4></td><td>Keep an eye on how competitors evolve their UX, features, and pricing. Spot trends and gaps early to inform roadmap decisions.</td></tr><tr><td><h4>Sales &#x26; BD Teams</h4></td><td>Spot new opportunities for outreach—like case studies, hires, or partnerships—as soon as they go live.</td></tr><tr><td><h4>Content &#x26; SEO Teams</h4></td><td>Track when relevant sites publish new content. Use it to plan timely responses or stay competitive on keywords.</td></tr><tr><td><h4>Investors &#x26; Analysts</h4></td><td>Monitor startup websites for traction signals—like new customers, hiring activity, or messaging shifts.</td></tr><tr><td><h4>Recruiters &#x26; Talent Teams</h4></td><td>See when companies update careers pages or announce new exec hires—ideal timing for outreach.</td></tr></tbody></table>

## Set up guide

{% stepper %}
{% step %}
### Log in to [CodeWords](https://codewords.agemo.ai/) and go to the [ Website Watcher Workflow](https://codewords.agemo.ai/run/website_monitoring_to_slack_trigger)
{% endstep %}

{% step %}
### Complete your set up&#x20;

1. **Add CodeWords to your Slack workspace**\
   Add CodeWords to your Slack workspace using the 'Add to Slack' button. You will need to give permission to CodeWords to access your slack workspace.&#x20;

<img src="../../.gitbook/assets/Screenshot 2025-05-28 at 12.28.28.png" alt="" data-size="original">

2. **Connect your Slack account** \
   You can do this via the Set Up section.

<img src="../../.gitbook/assets/Screenshot 2025-05-28 at 15.40.42.png" alt="" data-size="original">

2. **(optional) Create a new Slack channel**\
   Create a **public** Slack channel for the notifications to be sent to. You can also use an existing one if you prefer.
3. **Add the CodeWords bot to your selected Slack channel**\
   In the channel, simply type "/invite @CodeWords". You should then see a confirmation that CodeWords has been added to the channel.
{% endstep %}

{% step %}
### Complete the Input section

1. **Add in the URL(s) you want to monitor.** You can just monitor one, or multiple. We recommend starting with a small number to test out the workflow first.&#x20;
2. Specify the **slack channel** where you want to get notifications about detected changes
3. **(optional) Specify changes you want to track** \
   Describe the exact section of the website you want to track (e.g. pricing changes, product updates)
{% endstep %}

{% step %}
### Click Run

Wait about a minute the workflow to run and get set up.&#x20;
{% endstep %}

{% step %}
### Check the Output for Confirmation

1. You should see a **confirmation** that everything has been set up correctly in 'Status'
2. You can check **Slack preview** for an example of the output
3. Also check your **Slack channel** for a confirmation that everything has been set up correctly&#x20;
{% endstep %}

{% step %}
### That's it - now you'll just get a slack notification anytime a change happens on your specified website(s).&#x20;
{% endstep %}
{% endstepper %}

{% hint style="info" %}
If you encounter any issues, please reach out to us at support@agemo.ai, or if you're a beta user, get in touch with one of our team members on Slack.
{% endhint %}

## FAQs

<details>

<summary>How is this different from tools like ScrapeX or ChangeDetection.io?</summary>

Website Watcher is built for teams who live in Slack. Unlike generic page monitoring tools, it summarizes meaningful changes in plain English and delivers them directly to your Slack channel—no dashboards to check, no code to configure. It’s designed for real-time collaboration, not just passive tracking.

You also only pay for this single workflow and how much you use it, instead of a recurring SaaS bill.

</details>

<details>

<summary>Why not just subscribe to their newsletter?</summary>

Newsletters are delayed (and often filtered). Website Watcher gives you real-time alerts for competitive or strategic updates.

</details>

<details>

<summary>How often does it check for changes?</summary>

The agent checks your selected everyday and sends alerts when there's a meaningful update—not just minor text edits.

</details>

<details>

<summary>What if I want to schedule when the agent checks the website? </summary>

You can use [this workflow](https://codewords.agemo.ai/run/website_monitoring_to_slack) for that.

</details>

<details>

<summary>Can I track more than one site?</summary>

Yes. You can set up multiple workflows to monitor different websites or pages.

</details>

<details>

<summary>Can I choose which types of changes trigger alerts?</summary>

Yes. When you're setting it up, specify what kind of changes you're looking for. Simply specify in natural language what you want to track.

</details>

<details>

<summary>Will it monitor behind login pages or paywalls?</summary>

Not at the moment. In a future version it will be able to use your credentials to access pages behind a login in a safe and secure manner within your browser.

</details>

<details>

<summary>What if the page requires interaction (like clicking “View More”)?</summary>

We’re rolling out an advanced version of this workflow that can actively interact with pages—like clicking buttons or expanding sections. If that’s something you need, let us know and we’ll get you early access.

</details>

<details>

<summary>How do I turn off Website Watcher?</summary>

You can simply go to 'Scheduled Runs' on CodeWords, and disable the workflow.

</details>

<details>

<summary>What if it misses something or sends a false alert?</summary>

If you notice something off, just let us know via the chat widget on CodeWords, at support@agemo.ai or on Slack if you're in our Beta group. We’re constantly improving detection.

</details>

<details>

<summary>I like the workflow but want to tweak something (like the output format or inputs). Is that possible?</summary>

Yes! Just reach out via the chat widget on CodeWords and type in the variation you'd like. Plus, we're rolling out an edit feature soon, so you'll be able to customize workflows on your own with just a few clicks or message.

</details>
