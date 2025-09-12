# Quickstart

## Building your first automation

In this guide, you'll learn how to build your first lead follow-up workflow automation.

-Video Here-

You'll create an automation that:

* **Captures new leads from contact forms** and automatically starts the qualification process
* **Researches prospects on LinkedIn** using their name and company to find their complete professional profile and recent activity
* **Enriches with company intelligence** by analyzing their company website, recent news, and industry information using web scraping
* **Updates your CRM automatically** (Salesforce, HubSpot, or Pipedream integrations) with detailed prospect notes and lead scoring
* **Generates personalized follow-up emails** using AI that references their LinkedIn activity, company challenges, and industry trends
* **Sends an email with professional formatting** and your signature (Gmail, Outlook)
* **Sets follow-up reminders in your calendar** (Google Calendar, Outlook) and CRM to ensure consistent lead nurturing

## Step 1: Planning your automation

**Describe your process and tell Cody what you want to automate**

> "I want to automate my lead follow-up process. When someone fills out my contact form, I want to automatically research them and send a personalized email."

**Cody researches what's possible**

Cody will:

* Check if there are existing templates that match your needs (15+ proven templates available)
* Explore the 2000+ app integrations available through the platform
* Verify all the connections and data sources needed

**Review the automation plan**

Cody presents a plan:

1. **LinkedIn research:** Find their profile from name + company
2. **CRM integration:** Save contact + research notes
3. **Email generation:** Create personalized outreach
4. **Follow-up reminder:** Set a calendar reminder for 3 days

Once you approve, Cody starts building.

## Step 2: Incremental building

**LinkedIn Research**

**What Cody builds:**

* Takes name and company from form submission
* Finds their LinkedIn profile
* Extracts job title, company info, and recent posts

Cody tests with a sample Input:

```
Input: "John Smith from Acme Corp"

Results:
✅ Found LinkedIn Profile: John Smith, VP of Sales at Acme Corp
✅ Company: Acme Corp (500+ employees, Software)  
✅ Recent activity: Posted about Q4 sales goals
✅ Confidence: 95% match
```

**CRM Integration**&#x20;

**What Cody adds:**

* Creates a new contact record
* Adds research notes automatically
* Tags them as "Website Lead - Researched"

**Cody** **Testing results:**

```
✅ Created CRM Contact: John Smith
✅ Added Company: Acme Corp
✅ Added Notes: "VP of Sales, 500+ employee software company, recently posted about Q4 sales goals"
✅ Tagged as: Website Lead - Researched
```

**Personalized email**

**What Cody adds:**

* AI email generation using research data
* Matches your communication style
* Includes relevant talking points

**Sample output:**

<pre data-overflow="wrap"><code>Subject: Helping Acme Corp hit those Q4 sales goals

Hi John,
<strong>
</strong>I saw your recent LinkedIn post about Q4 sales goals at Acme Corp — it sounds like you're driving some ambitious targets for your team.

As a VP of Sales at a growing software company, you're probably facing the challenge of scaling your sales processes while maintaining quality.

I help companies like Acme Corp streamline their lead qualification and follow-up workflows so sales teams can focus on closing deals instead of manual research.

Would you be open to a brief 15-minute call this week to discuss how we might help Acme Corp hit those Q4 targets?

Best regards,
[Your name]
</code></pre>

#### **Follow-up reminder**

**What Cody adds:**

* Set a calendar reminder for 3 days
* Includes contact info and research notes
* Creates a task in your CRM

## Step 3: Final testing

Cody runs the complete workflow end-to-end to ensure everything works together seamlessly.

Cody asks for final confirmation:

{% code overflow="wrap" %}
```
The complete automation worked perfectly with Sarah's real data. The LinkedIn research found the right person, saved everything to your CRM with detailed notes, sent a personalized email mentioning her operational focus, and set your 3-day follow-up reminder. Are you completely satisfied with how this automation works?

1. Yes, it's exactly what I wanted.                
2. I'd like to adjust something first
```
{% endcode %}

## Step 4: Congratulations, Your Automation is Ready

Once you've confirmed that you're happy with the output, Cody will provide you with your automation URL:

```
https://codewords.agemo.ai/run/lead-qualifier-automation-abc123
```

## Step 5: Troubleshooting

**LinkedIn profiles not found**

* Check that the contact form captures both name and company
* Verify integration permissions
* Try manual search to confirm profile exists

**CRM integration issues**

* Confirm API credentials are current
* Check field mapping in your CRM settings
* Test with a simple contact creation first

**Email generation problems**

* Review your communication style examples
* Adjust the tone settings in email preferences
* Test with different contact data

## Summary

Cody provides you with a summary of the automation that you have built.

&#x20;You've built a complete lead management automation that:

* Research prospects automatically
* Updates your CRM with enriched data
* Sends personalized follow-up emails
* Sets reminders for future outreach

