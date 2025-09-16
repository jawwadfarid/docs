# Person Finder from Slack

<a href="https://codewords.agemo.ai/run/person_finder_from_slack" class="button primary">Use this template</a>

### Overview

This automation watches a Slack channel for mentions of people and, using AI, turns that chatter into quick, useful profile summaries you can post right back in the thread. It saves you from hunting down LinkedIn links or basic background details every time a new name pops up. Behind the scenes, it runs on a small FastAPI app, talks to Slack through a bot, and uses CodeWords’ AI runtime to extract names and context so you get fast, tidy results without leaving Slack.

### Description

This automation finds and summarizes people mentioned in Slack by combining Slack messages, AI technology, and a lightweight web app into a quick reply in your channel. It first listens for messages in the channel you register, then sends the message text to AI to pull out a person’s name, any helpful context, and a likely profile link. In parallel, it gets the right Slack channel and thread to post in. After processing the details and formatting the response, it posts a short, readable summary back to the thread to produce a quick profile snapshot that helps your team move faster without tab-hopping.

### Key Features

**Slack channel registration**: Point the automation at a specific Slack channel so it only runs where you want it.

**AI-powered name extraction**: Uses AI technology to identify the person mentioned, pull context, and infer useful details from the conversation.

**Threaded replies**: Posts results back into the original Slack thread, keeping context tidy and easy to follow.

**Custom output formatting**: Optionally guide how the summary should look (for example, “only show name, title, and company”).

**Access controls**: Choose whether only you can trigger it or anyone in the channel can, so you can keep it as open or controlled as you prefer.

**CodeWords runtime for AI**: Runs through CodeWords’ AI runtime with OpenAI-compatible APIs for consistent, reliable analysis.

**Simple FastAPI webhook**: A clean, documented HTTP endpoint Slack can call for events, making setup straightforward.

**Observable logging**: Structured logs via structlog so you can see what happened when messages are processed.

### Instructions

{% stepper %}
{% step %}
Open the automation and connect your Slack workspace by adding your Slack bot token.
{% endstep %}

{% step %}
Paste in your CodeWords API key and runtime URL so AI features work as expected.
{% endstep %}

{% step %}
Pick the channel you want to watch (like #general or #hiring) and hit Register to turn it on.
{% endstep %}

{% step %}
If you like, add simple formatting instructions (for example, “Show name and LinkedIn only”) to shape how results appear.
{% endstep %}

{% step %}
Mention someone naturally in the channel with a bit of context (for example, “Can someone connect me with Jordan Miller at Acme?”).
{% endstep %}

{% step %}
Check the thread for a short profile summary and link—use it as-is or refine your message and try again.
{% endstep %}
{% endstepper %}

### Use Cases

This automation is perfect for sales teams, recruiters, founders, and community managers who live in Slack and constantly swap names and intros. It saves time by pulling quick background context right inside the conversation. Great for warm intros, quick research before a meeting, or sanity-checking that you’ve got the right person without opening a dozen tabs.

### Frequently Asked Questions

<details>

<summary><strong>How does this automation know who to look up?</strong></summary>

It uses AI technology to read the message and extract the person’s name and context, then formats a helpful summary for the thread.

</details>

<details>

<summary><strong>Will it post publicly or in a thread?</strong></summary>

It posts back to the same channel and can reply in the thread of the original message to keep things neat.

</details>

<details>

<summary><strong>Can I control who can trigger it?</strong></summary>

Yes. During registration, you can choose whether anyone in the channel can trigger it or only you can.

</details>

<details>

<summary><strong>What if I want a specific format for the summary?</strong></summary>

You can add a short instruction like “Only show name, title, and company.” The automation will use that guidance when posting results.

</details>

<details>

<summary><strong>Do I need an OpenAI account?</strong></summary>

No. The automation uses CodeWords’ AI runtime with an OpenAI-compatible client. You just provide your CODEWORDS\_API\_KEY and CODEWORDS\_RUNTIME\_URL.

</details>

<details>

<summary><strong>Which Slack permissions are required?</strong></summary>

At minimum, the bot needs to read channel conversations, list channels to find the ID, and post messages (conversations: read/channels: read and chat: write).

</details>

<details>

<summary><strong>Does it work in private channels?</strong></summary>

Yes, as long as the bot is invited to the private channel and has permission to read and post there.

</details>

<details>

<summary><strong>What happens if it can’t find a profile?</strong></summary>

The automation will still reply with whatever context it can extract and let you know it couldn’t find a confident match, so you can adjust your prompt or add details.

</details>

<details>

<summary><strong>Can I run this in multiple channels?</strong></summary>

Yes. Register each channel you want to monitor. The automation looks up the channel ID and posts results there.

</details>

<details>

<summary><strong>How do I troubleshoot if nothing posts?</strong></summary>

Check that the bot is in the channel, verify your Slack token and CodeWords API key, confirm event subscriptions are hitting the /slack\_event endpoint, and look at logs for errors (structlog output).

</details>
