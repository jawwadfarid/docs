---
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

This guide provides a systematic approach to diagnosing and resolving issues within CodeWords workflows. Follow these steps to identify the root cause of a problem, whether it's a clear error or unexpected behaviour.

***

#### 1. The First Step: Ask Cody

Before diving into manual checks, always leverage the platform's built-in diagnostic capabilities. Cody can analyze the last execution, interpret error messages, and often provide a direct explanation and solution.

Within the same chat or in a new one, ask Cody about:

**What you can build**

* "Can I automate sending LinkedIn messages to new connections?"
* "I want to automatically track competitor pricing and notify my team"
* "Can you create something that finds email addresses from company websites?"

**CodeWords capabilities**

* "What kinds of automations can CodeWords do?"
* "Can CodeWords connect to my CRM/Slack/Google Sheets?"
* "Is it possible to scrape websites automatically?"

**Running and testing Workflows**

* "Can you run this workflow \[your workflow URL] with my data?"
* "Something isn't working. Check the logs and fix it?"
* "Can you modify my existing workflow at this URL \[your workflow URL]?"

**Learning and Guidance**

* "How do I get my API keys for \[your workflow URL]?"
* "What's the best way to automate \[specific business process]?"&#x20;

{% hint style="info" %}
If all else fails, ask us in [Discord](https://discord.codewords.ai/) in the #support channel.
{% endhint %}

***

#### 2. Investigating Unexpected Outputs

Sometimes a workflow completes successfully but produces strange or incorrect results. This requires a different approach.

Diagnostic Checklist:

* Validate the Input Data: Was the initial data that triggered the workflow correct and in the expected format?
* Trace the Data Flow: Use the execution logs to follow the data from step to step. Where did it get modified unexpectedly? Was a step skipped due to incorrect logic (e.g., a filter)?
* Isolate with Simple Data: Rerun the workflow with a very simple, predictable trigger. For example, use "Test Name" instead of a complex variable. If the simple test works, the issue lies in the complexity of your real data.
* Review Your Logic: Double-check any filters, conditional paths, or data transformation steps. Is the filter too restrictive? Is a variable being mapped to the wrong field?
* Consult the Examples: Review the documentation or examples for the specific service you're connecting to. Are you using the API or action correctly?

{% hint style="info" %}
If all fails, tell Cody what's happening and tell it to fix it.
{% endhint %}

***

#### 3. Escalation Procedure

If you have followed the steps above and cannot resolve the issue, it's time to escalate. To ensure a fast resolution, please provide the following information in your report.

Escalation Channels:

* Primary: Post in the support on the platform.
* Secondary: Use our [Discord](https://discord.codewords.ai/) Channel to post any issues.

Information to Include:

1. Workflow URL: A direct link to the workflow experiencing the issue.
2. Execution ID: The specific ID of the failed or incorrect run.
3. Problem Summary: A brief, one-sentence description of the issue.
4. Expected vs. Actual Behaviour: Clearly state what you expected to happen and what actually happened.
5. Troubleshooting Steps Taken: Briefly list the steps you've already tried from this guide. This prevents us from repeating work.
