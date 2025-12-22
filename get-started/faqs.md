---
description: Navigate to or search FAQs for questions related to any specific topic.
icon: comments-question-check
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# FAQs

### General Questions

<details>

<summary>What is CodeWords?</summary>

Turn natural language into automations so you can get more done. \
\
[CodeWords](https://codewords.agemo.ai/) is an AI-powered automation platform that helps teams and individuals build, deploy, and manage workflows faster. It's accessible to anyone — whether you’re a no-code creator, or a developer with technical expertise, CodeWords turns your natural language prompts into fully functional Python-based automations and intelligent AI agents.

</details>

<details>

<summary>How does CodeWords work?</summary>

Our AI automation assistant, Cody, builds, tests, debugs, and deploys your automations for you. It writes all the code, and allows you to build any automation that you describe.\
\
Ask for what you want, and CodeWords builds it, connects to your tools, and runs it whenever you want.&#x20;

</details>

<details>

<summary>Do I need coding knowledge to use CodeWords?</summary>

No. CodeWords is built with non-technical users in mind.\
\
It’s designed so anyone can create AI workflow automations and agents just by describing what you want in plain English — no coding required.\
\
Developers can still access and edit the Python code for deeper customization when needed.

</details>

<details>

<summary>How quickly can I build my first workflow?</summary>

Most users can build and deploy their first workflow in under ten minutes using Cody’s step-by-step conversational builder and pre-made templates.

</details>

<details>

<summary>What can I build with CodeWords?</summary>

CodeWords helps you build smart automations and AI agents that work with 2,700+ popular tools like LinkedIn, Google Workspace, WhatsApp, Slack, Telegram, and GitHub. You can automate anything — from simple data tasks to complex, AI-powered workflows or AI Agents that run your business in the background.

Each automation you create automatically includes a Run Page, where you can run it manually, schedule it, or trigger it based on app events. It also comes with an API endpoint, so you can interact with your automation through an external service with your codewords API key — all with no extra setup or coding required.

</details>

<details>

<summary>What makes CodeWords different from alternative automation tools like Zapier and Make?</summary>

Unlike traditional no-code tools that rely on rigid blocks or limited actions, CodeWords generates real Python automation code, empowering Cody to handle complex logic and deep integrations — all without writing a single line of code. Describe what you want in plain English, and Cody builds it for you.

</details>

<details>

<summary>Is CodeWords the same as UI generation tools like Lovable and v0?</summary>

No. CodeWords is designed to build automations and back-end workflows.\
\
You can easily connect to Lovable and v0 to create end-to-end solutions.&#x20;

</details>

<details>

<summary>Can I try CodeWords for free?</summary>

Yes. CodeWords offers a free tier with $5 in credits (no credit card required), allowing you to start building and testing workflows right away before adding more credits.&#x20;

</details>

<details>

<summary>How do I get started with CodeWords?</summary>

Sign up at [Codewords.ai](https://codewords.ai), explore the [Quickstart guide](https://docs.codewords.ai/get-started/quickstart-1), and chat with [Cody](https://docs.codewords.ai/fundamentals/introduction-to-cody) to build your first automation in minutes.

</details>

### Features and Capabilities

<details>

<summary>What Integrations does CodeWords support?</summary>

CodeWords supports 2700+ Integrations, including Gmail, Slack, Notion, Airtable, Google Sheets, Discord, WhatsApp, Mailchimp, Spotify, Hubspot and many more. You can find all the integrations that we support at our [Integrations](https://codewords.agemo.ai/account/integrations) page.

</details>

<details>

<summary>Can CodeWords integrate with custom UIs built on Lovable &#x26; V0 or external apps?</summary>

Yes. CodeWords can connect with apps built on Lovable, V0, or any external platform using two integration methods:

1. **CodeWords Client Library:** Offers quick, minimal-code integration for apps built with **Python** or **TypeScript/JavaScript**.
2. **REST API Calls:** Ideal for connecting CodeWords with apps built in **other programming languages**, using standard HTTP requests.

</details>

<details>

<summary>Can I create workflows that respond to external events?</summary>

Yes. Set up triggers for email arrivals, Slack messages, webhook events, form submissions, or schedule-based activations. Your workflows can react automatically to external events.

</details>

<details>

<summary>Do I need to worry about servers and infrastructure?</summary>

No! CodeWords handles all infrastructure automatically. Your workflows run on-demand in secure, isolated environments. No server management, scaling concerns, or maintenance required.

</details>

<details>

<summary>How do I get help if something goes wrong?</summary>

CodeWords provides detailed execution logs and error messages through the interface. Use the built-in support chat for technical help, or browse the extensive template library for examples and patterns.

</details>

<details>

<summary>Can I connect multiple workflows together?</summary>

Yes! Workflows can call other workflows, creating complex multi-step automations. Build modular components that work together for sophisticated business processes and data pipelines.

</details>

<details>

<summary>What if my workflow needs to process large amounts of data?</summary>

CodeWords automatically handles scaling and timeout management. For long-running tasks, the platform provides real-time progress updates and background processing to handle large datasets efficiently.

</details>

<details>

<summary>Why do I need the CodeWords Chrome Extension?</summary>



</details>

<details>

<summary>Can I generate my own custom UI?`</summary>

This is a feature coming soon. In the meantime, you can follow [this](/broken/pages/gLWWJ4HTgeBQ9OBHW78l) guide to integrate with popular UI generation tools.

</details>

### Running Workflows

<details>

<summary>How do I run a workflow?</summary>

Three ways:&#x20;

* Through an automatically generated custom UI available at `codewords.agemo.ai/run/{service_id}`
* On a [schedule](../core-concepts/schedules-and-triggers-1.md) or with a trigger
* via [API calls](/broken/pages/Sf11EFxFqhpU6StOQ8sD)

</details>

<details>

<summary>How do I schedule workflows to run automatically?</summary>

You can configure this after successfully building your workflow.

</details>

<details>

<summary>Can others use my workflows? </summary>

Yes, you can share workflows as private (you only), public (anyone can use), or templates (others can copy and modify). Each gets a permanent URL.

</details>

<details>

<summary>Can I call workflows via API? </summary>

Yes, every deployed workflow gets an API endpoint at https://runtime.codewords.ai/run/{service\_id} for programmatic access from external systems.

</details>

<details>

<summary>How do I get an API key?</summary>

Visit your account page [here](https://codewords.agemo.ai/account/keys) to generate API keys.

</details>

<details>

<summary>Is my data secure?</summary>

Yes, CodeWords uses secure environment variables for API keys and runs workflows in isolated sandboxes. Data is encrypted and each execution is completely isolated.

</details>

### Support

<details>

<summary>Where can I find support?</summary>

To get direct support from the team and the community, join our [Discord](https://discord.codewords.ai) channel or you can send us an email at [support@codewords.ai](mailto:support@codewords.ai)&#x20;

Our official documentation is at [docs.codewords.ai](https://docs.codewords.ai/). You can also find video tutorials on our YouTube channel at [@codewordsai](https://www.youtube.com/@codewordsai).

</details>

<details>

<summary>How can I reach out to the team?</summary>

You can find us on [Discord](https://discord.codewords.ai) or you can email us at support@codewords.ai

</details>

### About CodeWords

<details>

<summary>Can I make money from my workflows?</summary>

You can build custom automation solutions for clients using CodeWords as your platform. Our CodeWords creator program is also coming soon. More info [here](https://www.notion.so/agemo/CodeWords-Champions-2632b520705580e692f6fa8eb0528cd1?source=copy_link).

</details>

<details>

<summary>Where can I follow your work?</summary>

Check out the Agemo [blog](https://agemo.ai/blog) where we document our research, engineering and product work. Follow on [LinkedIn](https://linkedin.com/showcase/codewordsai) and [X](https://x.com/codewordsai) if you don't want to miss any updates.

</details>

<details>

<summary>Who is behind CodeWords?</summary>

[Agemo](https://agemo.ai/).

</details>

<details>

<summary>What stack is CodeWords using?</summary>

CodeWords builds workflows using FastAPI, Python and a mix of first-party and third-party providers for integrations and tools.

</details>
