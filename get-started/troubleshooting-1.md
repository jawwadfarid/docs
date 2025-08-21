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

This guide provides a systematic approach to diagnosing and resolving issues within Codewords workflows. Follow these steps to identify the root cause of a problem, whether it's a clear error or unexpected behaviour.

***

#### 1. The First Step: Ask the Codewords AI

Before diving into manual checks, always leverage the platform's built-in diagnostic capabilities. Codewords AI can analyse the last execution, interpret error messages, and often provide a direct explanation and solution.

How to Ask: Open the Codewords chat and use a prompt like the one below, replacing the placeholder with the specific URL of your workflow.

> "Check the last execution of the workflow with the URL: `[Your Workflow URL Here]`. Why did it fail and how can I fix it?"

***

#### 2. Investigating Unexpected Outputs

Sometimes a workflow completes successfully but produces strange or incorrect results. This requires a different approach.

Diagnostic Checklist:

* Validate the Input Data: The principle of "Garbage In, Garbage Out" applies. Was the initial data that triggered the workflow correct and in the expected format?
* Trace the Data Flow: Use the execution logs to follow the data from step to step. Where did it get modified unexpectedly? Was a step skipped due to incorrect logic (e.g., a filter)?
* Isolate with Simple Data: Rerun the workflow with a very simple, predictable trigger. For example, use "Test Name" instead of a complex variable. If the simple test works, the issue lies in the complexity of your real data.
* Review Your Logic: Double-check any filters, conditional paths, or data transformation steps. Is a filter too restrictive? Is a variable being mapped to the wrong field?
* Consult the Examples: Review the documentation or examples for the specific service you're connecting to. Are you using the API or action correctly?

***

#### 3. Escalation Procedure

If you have followed the steps above and cannot resolve the issue, it's time to escalate. To ensure a fast resolution, please provide the following information in your report.

Escalation Channels:

* Primary: Post in the `#dev-support` Slack channel.

Information to Include:

1. Workflow URL: A direct link to the workflow experiencing the issue.
2. Execution ID: The specific ID of the failed or incorrect run.
3. Problem Summary: A brief, one-sentence description of the issue.
4. Expected vs. Actual Behaviour: Clearly state what you expected to happen and what actually happened.
5. Troubleshooting Steps Taken: Briefly list the steps you've already tried from this guide. This prevents us from repeating work.
