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

# Creating Workflows

To get started, head over to [codewords.agemo.ai](http://codewords.agemo.ai/) and create an account.

Once registered, you will be able to create your first workflow.

This will be your first point of contact with the CodeWords agent, where you can chat to build workflows. Enter a prompt to get started, and CodeWords will do the rest!

## Prompting

CodeWords makes it simple by allowing you to build a workflow by prompting with the agent.

Be Specific About Your Goal

To get the best results from Cody, start with a clear, specific description of what you want to accomplish.

\
What **Doesn't Work**:

{% hint style="warning" %}
1. "I need something for social media"
2. "Make a workflow that helps with marketing"
3. "I want to automate my business"
{% endhint %}

What Works **Great**:

{% hint style="success" %}
1. _"Create a workflow that will label all my emails in my Gmail inbox every 30 minutes."_
2. "I need a workflow that finds email addresses for LinkedIn profiles in a spreadsheet"
3. "Build me something that monitors competitor websites and alerts me to price changes"
4. "Create a workflow that analyses customer feedback and categorises complaints"
{% endhint %}

The difference is clear: Cody needs to understand the specific business problem you're solving.

**Focus on Outcomes, Not Tools**&#x20;

Instead of asking for specific technologies, describe what you want to achieve&#x20;

**Don't Focus on the How:**

* "I need a web scraper"
* "Build me an AI thing"
* "I want to use the OpenAI API"

**Focus on the What:**

* "I want to extract product prices from competitor websites every week"
* "I want to analyse customer reviews and tell me the main themes"
* "I want to automatically respond to simple customer emails"

When you focus on what you want to achieve rather than how you think it should be built, Cody can choose the best tools and approach for your needs.

**Provide Context and Details** Give Cody enough information to make smart decisions about your workflow&#x20;

**Instead of Vague Requests:** "Build me a lead generation workflow"&#x20;

**Provide Rich Context:**&#x20;

{% hint style="info" %}
"Build me a lead generation workflow that:

* Finds marketing agency owners on LinkedIn
* In the US with 10-50 employees
* Gets their contact info and company details
* Outputs to a Google Sheet for my sales team
* Processes about 50 leads per week"
{% endhint %}

**Describe Your Current Process** Walk Cody through exactly what you do now, step by step&#x20;

**Example:** "Right now I manually:

1. Check our Twitter analytics for mentions and engagement
2. Look at LinkedIn post performance
3. Put it all in a PowerPoint for my weekly team meeting
4. This takes me 2 hours every Monday morning

I want a workflow that does this automatically and emails me the report."

**Be Specific About Data** Show Cody exactly what data you're working with, including examples **Good**&#x20;

**Example:** "I have a Google Spreadsheet with:

* Column A: Customer names
* Column B: Their LinkedIn URLs
* Column C: Company names
* About 200 rows updated weekly

I want to add job titles and company size in columns D and E."

**Clear Integration Requirements** Specify exactly where results should go and what notifications you need **Example:** "When the workflow finds new leads, I want it to:

* Add them to my HubSpot CRM in the 'Marketing Qualified' pipeline
* Send a Slack message to our #sales channel with the count
* Email me a summary if it finds more than 10 high-priority leads"

#### **The Perfect Request Template**

Use this structure to get the best results:

**What I Want to Accomplish:** \[Clear business goal]

**My Current Process:** \[Step by step what you do manually now]

**My Data/Inputs:** \[What information you're starting with, with examples]

**Desired Outputs:** \[Exactly what you want to get back]

**Integration Needs:** \[Where results should go, notifications needed]

**Success Criteria:** \[How you'll know it's working well]

{% hint style="info" %}
**What I Want to Accomplish:** Monitor competitor pricing and get alerts when prices change

**My Current Process:** Every Friday, manually check 5 competitor websites for prices on 20 products, record in spreadsheet

**My Data/Inputs:** Google Sheet with product names, competitor URLs, current prices

**Desired Outputs:** Updated prices, email alerts for 10%+ drops, weekly summary

**Integration Needs:** Update Google Sheet, email me and sales manager, Slack notification

**Success Criteria:** Catches changes within 24 hours, 95% accurate, no false alerts
{% endhint %}

Start simple and add features progressively. Provide business context so Cody understands your industry and challenges.

{% hint style="info" %}
**Example:** "I run a digital marketing agency managing social media for 25 local restaurants. My biggest challenge is creating enough content while tracking what performs best."
{% endhint %}

Inorder to understand what apps CodeWords can work with, Simply ask in the chat if it can connect to any specific apps.

\
"Can CodeWords connect to my Google Sheets/Hubspot/Slack app?"

## Customising a Template

You can customise any existing workflow template by clicking the 'edit' button, or you can click into Cody. The customised option on a workflow template or on a workflow that's yours allows you to change that automation to your vision. Just describe how you want to customise it!

This is a great way to explore the capabilities that you want to build.
