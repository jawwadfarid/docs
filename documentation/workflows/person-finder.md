---
description: >-
  Instantly generate a rich, professional profile for anyone—without the manual
  digging. This workflow combines social links, career history, recent activity,
  and professional focus—all in one place.
icon: user
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

# Person Finder

## Who is this for?

<table data-view="cards"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><h4>Sales &#x26; BD Teams</h4></td><td><p>Prep for calls or outreach in minutes. Get a verified snapshot of a prospect’s background and what they’ve been talking about recently.</p><h4></h4></td></tr><tr><td><h4>Marketers </h4></td><td><p>Quickly research collaborators, influencers, or customers. Get instant insight into their tone, interests, and digital presence.</p><h4></h4></td></tr><tr><td><h4>Founders &#x26; Execs</h4></td><td>Prep for meetings with partners, investors, or hires by scanning clean, contextual profiles in seconds.</td></tr><tr><td><h4>Recruiters &#x26; Hiring Managers</h4></td><td><p>Scan a full picture of a candidate—background, skills, social footprint—before you even say hello.</p><h4></h4></td></tr><tr><td><h4>VCs &#x26; Analysts</h4></td><td><p>Understand team dynamics and founder history before intro calls or during due diligence.</p><h4></h4></td></tr><tr><td><h4>User Researchers &#x26; Product Teams</h4></td><td>Prep for interviews with rich context on participants—background, posts, skills—without manual searching.</td></tr></tbody></table>

## Set up guide

### Option 1: In Your Browser&#x20;

{% stepper %}
{% step %}
### Visit CodeWords and go to the [Person Finder Workflow](https://codewords.agemo.ai/run/person_finder)&#x20;
{% endstep %}

{% step %}
### Complete your set up&#x20;

Download the CodeWords Chrome Extension if you haven't already.

<figure><img src="../../.gitbook/assets/Screenshot 2025-05-28 at 12.13.51.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Complete the Input section

Add in the person's full name and any additional info you have, such as location or company. There's an optional field to add in the LinkedIn URL too.
{% endstep %}

{% step %}
### Click Run

Wait about 3-5 minutes for the workflow to run. You can leave the tab open and continue your work in the background.&#x20;
{% endstep %}

{% step %}
### Check the Output

You'll see a detailed profile report with social links, professional summary, work history, and recent public activity in the Output section when the workflow is complete.
{% endstep %}
{% endstepper %}

### Option 2: On Slack

{% embed url="https://youtu.be/TS2o4mZhJes" %}

{% stepper %}
{% step %}
### Visit CodeWords and go to the [Person Finder from Slack Workflow](https://codewords.agemo.ai/run/person_finder)&#x20;


{% endstep %}

{% step %}
### Complete your set up&#x20;

1. **Add CodeWords to your Slack workspace**\
   Add CodeWords to your Slack workspace using the 'Add to Slack' button. You will need to give permission to CodeWords to access your slack workspace.&#x20;

<img src="../../.gitbook/assets/Screenshot 2025-05-28 at 12.28.28.png" alt="" data-size="original">

2. **Connect your Slack account and download the CodeWords Chrome Extension**\
   You can do this via the Set Up section.

<figure><img src="../../.gitbook/assets/Screenshot 2025-05-28 at 12.30.32.png" alt=""><figcaption></figcaption></figure>

3. **(optional) Create a new Slack channel**\
   Create a **public** Slack channel for the notifications to be sent to. You can also use an existing one if you prefer.
4. **Add the CodeWords bot to your selected Slack channel**\
   In the channel, simply type "/invite @CodeWords". You should then see a confirmation that CodeWords has been added to the channel.
{% endstep %}

{% step %}
### Complete the Input section

Add in the name of the name of the channel where you want to use Person Finder.&#x20;
{% endstep %}

{% step %}
### Click Run

Wait about a minute the workflow to run and get set up.&#x20;
{% endstep %}

{% step %}
### Check the Output for Instructions

1. **Ensure the CodeWords bot is invited to your selected channel**
   * If not, type `/invite @CodeWords` to add our bot
2. **Start using the workflow**
   * Mention a person naturally in the channel.
   * For example:
     * "Can anyone find information about Jane Smith who works at Google as an AI researcher?"
     * "Looking for John Doe who recently published a paper on quantum computing at MIT"
     * "Amir Patel, London, DeepMind"
3. **Get automatic results**
   * The workflow will be triggered automatically when a message is posted in the channel
   * When it detects a message with a person's name and details, it will:
     * Find their social profiles (Twitter, LinkedIn, GitHub, Google Scholar)
     * Analyze their professional background, recent activity, and interests
     * Post a comprehensive summary back to your channel
4. **Make sure to have an active browser window**
   * The workflow will open a browser window to search for the person's social profiles
   * If the browser window is not active, the workflow will not be able to find the profiles
{% endstep %}

{% step %}
### Test out Person Finder in your Slack Channel&#x20;

It's best to test out this workflow on Slack to see if it's working as you expected. Just go to your Slack channel and search a person to trigger the workflow.&#x20;
{% endstep %}
{% endstepper %}

<figure><img src="../../.gitbook/assets/Screenshot 2025-05-28 at 12.38.23.png" alt=""><figcaption></figcaption></figure>

If you encounter any issues, please reach out to us at support@agemo.ai, or if you're a beta user, get in touch with one of our team members on Slack.

## FAQs

<details>

<summary>Why would I use this instead of just looking someone up on LinkedIn?</summary>

Person Finder pulls in information from multiple sources—not just LinkedIn. You get a richer, more complete view (social links, posts, skills, career history) in one place, without needing to bounce between tabs.

</details>

<details>

<summary>How much time could this actually save me? </summary>

On average, users save up to 30 minutes per person. It removes the need to search across platforms and piece together context manually—especially helpful when prepping for multiple calls in a row.

</details>

<details>

<summary>Where does the data come from?</summary>

Person Finder pulls publicly available information from sources like LinkedIn, Twitter, company bios, and more—then compiles it into a clean, scannable format.

</details>

<details>

<summary>Is this compliant with privacy rules?</summary>

Yes—all data surfaced is publicly available. We don’t scrape private info or violate platform policies.

</details>

<details>

<summary>Will the person know I looked them up?</summary>

No—Person Finder doesn’t trigger profile view notifications (like LinkedIn often does). Your research stays private.

</details>

<details>

<summary>Can I use this directly in Slack?</summary>

Yes—that’s the beauty of it. You can trigger the workflow by searching a name in Slack and get the full profile directly in-thread, without switching tools.

</details>

<details>

<summary>What if I already know the person?</summary>

Even if you do, Person Finder is helpful for refreshing context—especially on recent posts, new roles, or shared links you may have missed.

</details>

<details>

<summary>What do I do if I encounter any issues or get an error? </summary>

Reach out at support@agemo.ai, or message our team on Slack if you're in the beta group.

</details>

<details>

<summary>I like the workflow but want to tweak something (like the output format or inputs). Is that possible?</summary>

Yes! Just reach out via the chat widget on CodeWords and type in the variation you'd like. Plus, we're rolling out an edit feature soon, so you'll be able to customize workflows on your own with just a few clicks or message.

</details>
