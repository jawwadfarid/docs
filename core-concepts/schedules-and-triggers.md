---
description: You can run workflows automatically by setting up schedules and triggers.
icon: bolt
---

# Schedules and triggers

{% embed url="https://www.youtube.com/watch?v=9fiFQPeD4Cg" %}

### **Overview**

We've already covered r[unning automations](https://docs.codewords.ai/~/revisions/CBsznWzxyNtIJHNMAo7I/core-concepts/running-automations) manually, but you can also set up schedules and triggers to run your automations in the background.&#x20;

* **Schedules:** These are automations that you set up to run at a specific time and frequency. For example, every day at 9am.
* **Triggers:** These automations are set-off after a specific action is completed. For example, reacting to a Slack message with a specific emoji.&#x20;

These features allow you to create an autonomous system around your day-to-day life or work.&#x20;

### Schedules&#x20;

Schedules let you run workflows automatically at set intervals. This is ideal for reports, reminders, or maintenance tasks.

You can choose how often your workflow automation should run, and at what time and frequency:

* Hourly
* Daily
* Weekly
* Monthly
* Custom interval&#x20;

#### Setting up schedules&#x20;

It's easy to set up schedules for your automations from within CodeWords.&#x20;

Simply head to your automation's run page, and select `Schedule` in the top-right corner.&#x20;

From there:

* Decide how often you'd like the automation to run. You can choose to run the automation once at a specific time, or on a recurring schedule.&#x20;
* Finish adding any inputs.&#x20;
* You can tick or untick whether you'd like to receive email confirmations when your workflow runs.&#x20;
* Click `Save` .

Whilst you're building an automation with Cody in the chat, you can also ask Cody there to set up the schedule for you.&#x20;

<figure><img src="../.gitbook/assets/schedule (1).gif" alt="Setting up a schedule on CodeWords"><figcaption><p>Setting up a scheduled workflow on CodeWords</p></figcaption></figure>

#### Managing schedules&#x20;

You'll find an overview of all your current schedules on the [**Scheduled Runs**](https://codewords.agemo.ai/workflows/schedule) page.

From here:

* You can see when your workflow last ran and when it's next scheduled to run.
* You can search for schedules.
* You can toggle on or off the schedule.&#x20;
* You can select three dots and
  * Edit the schedule.
  * Resume the schedule.
  * Delete the schedule.
  * Disable email notifications for the schedule.

### Triggers

Triggers allow your automations to start running when a specific action is completed. For example, when a message is sent, a form is submitted, or a new record is created.

You can ask Cody to set up a trigger for your workflow either during the building process or as a later edit.&#x20;

Once your trigger has been set up, you'll be able to test that it works with Cody. You can use real or fake data, and Cody will be able to confirm or debug the setup.&#x20;

#### **Examples of triggers**

Let's go through some more specific examples for different triggers, depending on the integrations you'd like to use in your workflows.&#x20;

* **Slack:** New messages, reactions, or when a user joins a channel
* **WhatsApp:** Incoming messages sent to the CodeWords WhatsApp number, group messages where CodeWords is a member, and message reactions.
* **Gmail:** New emails, label changes, or draft creation
* **Google Calendar:** Event creation, updates, or deletions
* **GitHub:** Code pushes, new issues, pull requests
* **Notion:** Page or database updates
* **Discord, HubSpot, Stripe, Airtable**, and many more

In general, you don't need to check beforehand whether you can set up a specific trigger. Just ask Cody in the chat interface to set one up, or ask for examples you could use.&#x20;

If your app supports event-based actions, CodeWords can likely trigger from it.

#### Managing triggers&#x20;

You'll find an overview of all your current triggers on the [**Triggers**](https://codewords.agemo.ai/workflows/triggers) page.

From here:

* You can check whether the trigger is active and when it previously ran.
* You can search for triggers.
* You can see how often the trigger has been actioned.
* You can toggle on or off the workflow trigger.
* You can select three dots and
  * Pause the trigger.
  * Delete the trigger.
  * Disable the email notification.

#### **Custom Webhooks**

If your system isn’t natively supported, CodeWords provides custom webhook URLs to handle external events.

\
These URLs can be called from any platform capable of sending HTTP POST requests with JSON data.

To create one, simply tell Cody which external system you want to connect. Cody will automatically generate and configure the webhook endpoint for you.

To learn more about Webhooks in CodeWords, visit the [Webhooks](https://docs.codewords.ai/fundamentals/webhooks) documentation page.



### **When to use each**

| Use Case                                   | Best Option            |
| ------------------------------------------ | ---------------------- |
| Reacting instantly to new data or messages | Event-driven trigger   |
| Running recurring reports or reminders     | Scheduled trigger      |
| Connecting unsupported systems             | Custom webhook trigger |

Event-driven triggers are best for responsive workflows. Scheduled triggers are ideal for predictable, time-based automation.

### FAQs

<details>

<summary>What if my app isn’t supported?</summary>

You can use custom webhooks. Cody will create a webhook URL you can connect to any system that sends HTTP POST requests with JSON data.

</details>

<details>

<summary>What are triggers?</summary>

Through Pipedream, you can use over 2,700+ event sources, including Gmail, Notion, GitHub, Stripe, and HubSpot. These expand your automation options far beyond native integrations.

</details>

<details>

<summary>Can I see or edit my active triggers?</summary>

Yes, visit the Triggers page in CodeWords to manage, pause, or delete any active event-based automation.

</details>

<details>

<summary>Do triggers run even when I’m offline?</summary>

Yes. Once set up, triggers and schedules run automatically in the background — no manual action needed.

</details>

