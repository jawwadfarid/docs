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

This guide provides a systematic approach to diagnosing and resolving issues within Codewords workflows. Follow these steps to identify the root cause of a problem, whether it's a clear error or unexpected behavior.

***

#### 1. The First Step: Ask the Codewords AI

Before diving into manual checks, always leverage the platform's built-in diagnostic capabilities. Codewords AI can analyze the last execution, interpret error messages, and often provide a direct explanation and solution.

How to Ask: Open the Codewords chat and use a prompt like the one below, replacing the placeholder with the specific URL of your workflow.

> "Check the last execution of the workflow with the URL: `[Your Workflow URL Here]`. Why did it fail and how can I fix it?"

***

#### 2. A Step-by-Step Diagnostic Process

If the AI's diagnosis is unclear or you need to dig deeper, follow this manual process.

**Step 1: Review the Execution Logs**

The execution logs are the single most important tool for troubleshooting. They provide a detailed, step-by-step record of a workflow's run, showing the input and output data for each action.

* Locate the Logs: Navigate to the specific workflow and click on the "History" or "Executions" tab.
* Identify the Failed Step: Find the specific execution that failed. The logs will highlight the exact step where the error occurred.
* Inspect the Data: Examine the data that was passed into the failed step. This is often the source of the problem.

**Step 2: Understand the Error Type**

Error messages are designed to tell you what went wrong. They generally fall into one of three categories:

| Error Category        | Common Messages                                                                     | Typical Cause                                                                                       | Action Required                                                                                                            |
| --------------------- | ----------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Input & Configuration | `Invalid Input`, `Required field missing`, `400 Bad Request`                        | The data sent to a step was incorrect, incomplete, or in the wrong format.                          | Check your inputs. Review the data from the previous step in the logs to ensure it matches what the failing step expects.  |
| Service & Execution   | `500 Internal Server Error`, `Stack Trace`, `Cannot read property 'x' of undefined` | There is a problem with the code or logic within the workflow step itself. This may indicate a bug. | Isolate the issue. Try running the step with a known-good, simple input. If it still fails, escalate the issue.            |
| Connectivity & API    | `Network Error`, `Connection Refused`, `403 Forbidden`, `API key invalid`           | The workflow could not connect to an external application or service.                               | Check the connection. Verify API keys, authentication tokens, and ensure the third-party service is online and accessible. |

Export to Sheets

***

#### 3. Investigating Unexpected Outputs

Sometimes a workflow completes successfully but produces strange or incorrect results. This requires a different approach.

Diagnostic Checklist:

* Validate the Input Data: The principle of "Garbage In, Garbage Out" applies. Was the initial data that triggered the workflow correct and in the expected format?
* Trace the Data Flow: Use the execution logs to follow the data from step to step. Where did it get modified unexpectedly? Was a step skipped due to incorrect logic (e.g., a filter)?
* Isolate with Simple Data: Rerun the workflow with a very simple, predictable trigger. For example, use "Test Name" instead of a complex variable. If the simple test works, the issue lies in the complexity of your real data.
* Review Your Logic: Double-check any filters, conditional paths, or data transformation steps. Is a filter too restrictive? Is a variable being mapped to the wrong field?
* Consult the Examples: Review the documentation or examples for the specific service you're connecting to. Are you using the API or action correctly?

***

#### 4. Escalation Procedure

If you have followed the steps above and cannot resolve the issue, it's time to escalate. To ensure a fast resolution, please provide the following information in your report.

Escalation Channels:

* Primary: Post in the `#dev-support` Slack channel.
* Secondary: File a ticket in Jira under the `[PROJECT-NAME]` board.

Information to Include:

1. Workflow URL: A direct link to the workflow experiencing the issue.
2. Execution ID: The specific ID of the failed or incorrect run.
3. Problem Summary: A brief, one-sentence description of the issue.
4. Expected vs. Actual Behavior: Clearly state what you expected to happen and what actually happened.
5. Troubleshooting Steps Taken: Briefly list the steps you've already tried from this guide. This prevents us from repeating work.
