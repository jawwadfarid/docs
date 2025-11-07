---
description: >-
  Learn how to test and run your CodeWords workflows with Cody or manually.
  Validate integrations, monitor execution logs, and troubleshoot errors with
  the detailed Run page.
icon: vial
---

# Testing and Running Workflows

### **Overview**

Once your workflow is built, CodeWords gives you two ways to test and run it — through **Cody** for automated validation, or manually through the **Run page** for detailed inspection. Both methods help ensure your automations perform reliably before deployment.

### **1. Testing Your Workflows**

#### Let Cody test for you

The fastest and most reliable way to validate your workflow is to ask Cody to test it automatically. Cody simulates real execution, verifying that all connections, steps, and data flows work as expected — without needing manual setup.

**You can say:**

* “Test this workflow with sample data and show me the results.”
* “Run a test using this example: \[paste your real data].”
* “Can you test this automation and check if it works correctly?”

**Cody automatically checks that:**

* All integrations are properly connected
* Data flows smoothly between steps
* Outputs match your expectations
* Error handling behaves correctly when something fails

This automated validation catches most issues before you ever run the workflow manually.

#### **Manual Testing Through the UI**

Once Cody’s automated tests succeed, you can manually verify with real data especially for production workflows or after major updates.

**When to test manually:**

* After Cody’s test passes, but before deploying
* When testing real-world scenarios or live integrations
* After editing or updating a workflow

**How to test manually:**

1.  Go to your workflow’s **Run page:**

    ```
    https://codewords.agemo.ai/run/{your-workflow-id}
    ```

* Prepare your test data using realistic examples.
* Click **Run** and monitor execution in real-time through progress logs.
* Verify that all outputs and actions match your expectations.
* Try a few input variations to ensure reliability under different conditions.

<figure><img src="../.gitbook/assets/run_wf.gif" alt=""><figcaption><p>Accessing the Run Page of a Workflow</p></figcaption></figure>

### **2. Running Workflows**

Once testing is complete, you can run your workflow directly either from the chat interface or through the **Run page** for detailed tracking.

#### **Run Directly from Chat**

You can trigger and test workflows directly from the same chat where they were created by switching to **Run Mode**. This allows for quick validation and immediate feedback on how your automation performs.

#### **Run Page Overview**

Each time a workflow is executed — manually, on schedule, or via a trigger — a new Run page is generated. This serves as a complete execution log and audit trail of the process.

**Each Run page includes:**

* **Status:** Success, Failed, or In Progress
* **Timestamps:** When each step was executed
* **Data flow:** Inputs and outputs for every step
* **Error details:** Full diagnostics if something failed

If an automation doesn’t behave as expected, the Run page is the first place to check for detailed logs and troubleshooting information.

<figure><img src="../.gitbook/assets/Area.gif" alt=""><figcaption><p>Accessing the Run Page within the chat</p></figcaption></figure>
