---
icon: screwdriver-wrench
layout:
  width: default
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# Troubleshooting

This guide provides a systematic approach to diagnosing and resolving issues within CodeWords workflows. Follow these steps to identify the root cause of a problem, whether it's a clear error or unexpected behavior.

***

#### Ask Cody

The easiest way to troubleshoot any errors you come across is by asking Cody in the chat.&#x20;

Cody can analyze the last execution, interpret error messages, and often provide a direct explanation and solution.&#x20;

Simply ask Cody to diagnose any errors and fix it.&#x20;

You can ask Cody about a range of things, including:&#x20;

**What you can build**

* "Can I automate sending LinkedIn messages to new connections?"
* "I want to automatically track competitor pricing and notify my team"
* "Can you create something that finds email addresses from company websites?"

**CodeWords capabilities**

* "What kinds of automations can CodeWords do?"
* "Can CodeWords connect to my CRM/Slack/Google Sheets?"
* "Is it possible to scrape websites automatically?"

**Running and testing workflows**

* "Can you run this workflow \[your workflow URL] with my data?"
* "Something isn't working. Check the logs and fix it?"
* "Can you modify my existing workflow at this URL \[your workflow URL]?"

**Learning and guidance**

* "How do I get my API keys for \[your workflow URL]?"
* "What's the best way to automate \[specific business process]?"&#x20;
* "Do you have access to \[e.g., X or Pinterest]?"

{% hint style="info" %}
You can also ask us in [Discord](https://discord.codewords.ai/) in the #support channel.
{% endhint %}

***

#### Resolving unexpected outputs

Sometimes a workflow completes successfully but produces results that weren't as you'd intended.&#x20;

For example, an output might not include the exact information you want, or it might not be visualized in the way you'd like.&#x20;



Diagnostic checklist:

* Ask Cody: Specify what's missing or what you'd like considered in future output versions.
* Validate the input data: Was the initial data that triggered the workflow correct and in the expected format?
* Trace the data flow: Use the execution logs to follow the data from step to step. Where did it get modified unexpectedly? Was a step skipped due to incorrect logic (e.g., a filter)?
* Isolate with simple data: Rerun the workflow with a very simple, predictable trigger. For example, use "Test Name" instead of a complex variable. If the simple test works, the issue lies in the complexity of your real data.
* Review your logic: Double-check any filters, conditional paths, or data transformation steps. Is the filter too restrictive? Is a variable being mapped to the wrong field?
* Consult the examples: Review the documentation or examples for the specific service you're connecting to. Are you using the API or action correctly?

{% hint style="info" %}
You can also tell Cody what's happening and tell it to fix it if you're unsure.&#x20;
{% endhint %}

***

#### Escalation procedure

If you have followed the steps above and cannot resolve the issue, you can use this escalation process to get more in-depth support.&#x20;

To ensure a fast resolution, please provide the following information in your report.

Escalation channels:

* Primary: Type your query/issue into the support chat (bottom-right).&#x20;
* Secondary: Use our [Discord](https://discord.codewords.ai/) channel to post any issues.

Information to include:

1. Workflow URL: A direct link to the workflow experiencing the issue.
2. Execution ID: The specific ID of the failed or incorrect run.
3. Problem summary: A brief, one-sentence description of the issue.
4. Expected vs. actual behavior: Clearly state what you expected to happen and what actually happened.
5. Troubleshooting steps taken: Briefly list the steps you've already tried from this guide. This prevents us from repeating work.
