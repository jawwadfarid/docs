# Testing & Debugging

### Testing your workflows

#### Let Cody test for you

The smart approach: Ask Cody to test your workflow before you do anything manual.

How to ask:

* "Test this workflow with sample data and show me the results."
* "Run a test using this example: \[paste your real data]"
* "Can you test this automation and check if it works correctly?"

What Cody validates:

* All integrations connect properly
* Data flows correctly between steps
* Output matches your expectations
* Error handling works when things go wrong

This catches most issues before you even run the workflow manually.

#### Manual testing through the UI

When you should test manually:

* After Cody's test passes, you want to verify with real data
* Before deploying important business automations
* When you've made changes to an existing workflow

Step-by-step manual testing:

1. Navigate to your workflow: `https://codewords.agemo.ai/run/{your-workflow-id}`
2. Prepare test data: Use real examples that represent your typical use cases
3. Run and monitor: Watch the live progress logs as your workflow executes
4. Verify outputs: Check that results match what you expected
5. Test variations: Try different input scenarios to ensure reliability
