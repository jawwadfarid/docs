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

If you encounter any issues with your automation workflow, such as errors or unexpected output, you can ask in the CodeWords chat.

{% hint style="info" %}
_"Check the last execution of the workflow with the URL: \[Input your workflow URL here]. Why did I get an error?"_
{% endhint %}

#### Reading Error Messages

Errors types:

* Input errors (your fault) : "Invalid input", "Required field missing" → Check your data
* Service errors (code problem) : "500 error", stack traces → Something in the workflow broke
* Connection errors : "Network error", "Connection refused" → Internet or server problem

What to do:

1. Read the error message carefully - it usually tells you exactly what's wrong
2. Check your inputs - Are you sending the right data format?
3. Try again - Sometimes it's just a temporary glitch
4. Look at the logs (see below) for more details

#### It Ran But Gave Weird Results:

What you see:

* Workflow completes but results don't make sense
* Missing data
* Unexpected output format

Detective work:

1. Check your input data - Garbage in, garbage out
2. Look at the progress logs - See what steps actually ran
3. Test with simpler data - Start small and build up
4. Check the examples - Are you using the workflow correctly?
