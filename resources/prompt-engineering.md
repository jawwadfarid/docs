---
description: >-
  It's easy to learn how to prompt engineer with CodeWords. This guide takes you
  through all our best tips and tricks.
icon: face-smile-relaxed
---

# Prompt engineering

***

One of the easiest ways to get more out of CodeWords is to learn some tips and tricks that help you prompt and communicate better with LLMs.&#x20;

It's best to view Cody as a way to get advice, ideate, and chat, _as well as_ an AI assistant that builds automations for you. This allows you to get the most out of the CodeWords platform.&#x20;

Let's go through some simple tips and best practices to help you prompt your way to perfect automations.&#x20;

### Start simple

You've heard of MVP (Minimum viable product), well we believe in a MVA (Minimum viable automation). This is the basic version of your build so you can test and fully understand what you want to change, adapt, or extend.&#x20;

The best way to build is by creating a simple version of your automation, and then adding features, complex logic, and further integrations once it's working.&#x20;

You can describe what you'd like to build and ask Cody what a simple version of this would look like if you're unsure.&#x20;

LLMs typically digest information better when it's delivered in chunks. Building the core functionality of your automation first helps you have more control over the output, and it also helps you reach your desired outcome quicker.&#x20;

### Provide numbered steps&#x20;

Sometimes it can be helpful to provide numbered steps for each part of your if it feels more complex.&#x20;

For example, if you're building an automation for content creation and you'd like Cody to use your brand guidelines at a certain step, you can get Cody to ask you for your guidelines when it's at that stage of the building process. This prevents your prompt from becoming too long, but keeps all the information concise and easy-to-follow.&#x20;

### Give extra context&#x20;

Sometimes the best way build automations is by giving Cody some extra context about your job role, a repetitive task you'd like to automate, or describing a day-to-day task that causes friction.

You can do this either at the start of the building process, or once your core workflow has been built so you can extend it.&#x20;

You can also work with Cody to ideate on solutions according to your industry and challenges.&#x20;

{% hint style="info" %}
**Example:** "I run a digital marketing agency managing social media for 25 local restaurants. My biggest challenge is creating enough content while tracking what performs best."
{% endhint %}

### Be specific if you know what you want to solve&#x20;

Sometimes you know the exact problem you're trying to solve and which tools you'll use to solve it.&#x20;

In these instances, you'll get to your end result faster if you're specific about your workflow.&#x20;

For example:&#x20;

{% hint style="info" %}
1. "Create a workflow that will scrape website X and summarise the content and email me the response"
2. "Build me a workflow that scrapes Google review data for restaurants and saves it into a CSV file "
3. "Build me something can extract text data from an image of a handwritten letter"
4. "Create a workflow that transcribes a YouTube video, distills it into notes, and stores it in my Google Doc"
{% endhint %}

If you're not sure what you want to fix specifically, but you have multiple friction points and don't know where to start, you can still provide Cody with vague aims.&#x20;

For example:&#x20;

{% hint style="info" %}
1. "I need something for social media"
2. "Make a workflow that helps with marketing"
3. "I want to automate my business"
{% endhint %}

In these cases, although Cody won't start building your automation instantly, it will ideate on the idea with you by asking you clarifying questions and offering automation ideas.&#x20;

We get that sometimes you need to chat through your ideas in order to organize them. This is why Cody helps you do that too.&#x20;

### Upload reference images&#x20;

You can easily attached reference images to the chat with the `+` button.&#x20;

This is useful for when you're using a specific integration, or if you found an automation example that you'd like to replicate.&#x20;

Uploading references can be a good way to help Cody visualize exactly what you'd like.&#x20;

Check out [this example](https://www.linkedin.com/posts/rebecca-pearson-308424232_openai-dropped-agentkit-yesterday-so-i-thought-activity-7381387714417491968-fvrg?utm_source=share\&utm_medium=member_desktop\&rcm=ACoAADoVTrgBefGnTrUJhBYInyE_x3K2zGj8LhY) where a reference from one of OpenAI's AgentBuilder automation demos is uploaded to the chat, and Cody builds a replica of this automation.&#x20;

### Isolate testing&#x20;

There are a couple of helpful ways you can isolate testing so that Cody focuses on fixing errors in one part of your workflow should they arise.&#x20;

You can:

* **Ask Cody to test integrations separately before it starts building**&#x20;
* **Ask Cody to isolate and debug a specific section that contains an error, and focus on it until it's fixed**

### Focus on outcomes, not tools&#x20;

Instead of asking for specific technologies, describe what you want to achieve. Often Cody will suggest alternatives way to build something or offer other solutions that might more closely fit your use case.

**Focus on&#x20;**_**what**_**:**

* "I want to extract product prices from competitor websites every week."
* "I want to analyze customer reviews and tell me the main themes."
* "I want to automatically respond to simple customer emails."

When you focus on what you want to achieve rather than how you want it to be built, Cody can choose the best tools and approach for your needs.

* **Provide extra details:** Give Cody enough information to make smart decisions about your workflow&#x20;
* **Provide detailed context:**&#x20;

{% hint style="info" %}
"Build me a lead generation workflow that:

* Finds marketing agency owners on LinkedIn
* In the US, with 10-50 employees
* Gets their contact info and company details
* Outputs to a Google Sheet for my sales team
* Processes about 50 leads per week."
{% endhint %}

### Be specific about data&#x20;

Whilst it's not a necessity, it can be helpful to provide extra detail about any data you're working with. This way Cody can align how your workflow is being built, and it can also offer further suggestions and considerations to refine it.&#x20;

You can show Cody exactly what data you're working with, including examples.

**Example:**&#x20;

I have a Google Spreadsheet with:

* Column A: Customer names
* Column B: Their LinkedIn URLs
* Column C: Company names
* About 200 rows are updated weekly

I want to add job titles and the company size in columns D and E.

Specify exactly where results should go, which integrations you use, and what notifications you need.&#x20;

**Example:**&#x20;

When the workflow finds new leads, I want it to:

* Add them to my HubSpot CRM in the 'Marketing Qualified' pipeline
* Send a Slack message to our #sales channel with the count
* Email me a summary if it finds more than 10 high-priority leads.

Cody will often ask further clarifying questions about information you've provided, just in case more information is needed about certain input fields or actions. This means you never have to worry about edge cases or missing information. If it's required, Cody will prompt you for it.&#x20;

### Version history

Sometimes you might want to revert back to an original version of your workflow.&#x20;

You can do so by providing Cody with the Implementation ID of the desired version.&#x20;

Then, ask Cody to change the workflow to that specific Implementation ID.&#x20;

You can also ask Cody to undo the last set of changes while you're in the chat.&#x20;





