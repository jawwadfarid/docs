---
description: Here you'll find all the key terms and concepts needed for using CodeWords.
---

# Glossary

### Core platform concepts

Here are all our key concepts, used throughout the platform. These points and more in-depth terms are included below within each category, but you'll find everything you need at a glance right here. &#x20;

**Cody** - The CodeWords AI automation assistant. Use Cody like you're using ChatGPT — ask questions, iterate on your automation ideas, ask to edit, customize, or update existing workflows.&#x20;

**Automations Workflow** - A sequence of connected steps that automatically perform tasks for you, like monitoring websites, processing emails, or extracting data from social media.

**CodeWords Platform** - A cloud-based automation system that lets you create and run workflows without managing servers or complex infrastructure.

**CodeWords Chrome Extension** - Access more automation capability. You can download the CodeWords chrome extension [here](https://chromewebstore.google.com/detail/codewords/fgcbeegcaikofigbnfmmlgcimdkmfnce?hl=en), but you'll also be prompted within the platform.&#x20;

**Workflow Templates** - Pre-built, fully functional workflows you can use as-is or modify for your specific needs. These are packaged in our user interface so that each workflow template has its own run page where you can choose your inputs and actively run the automation.&#x20;

**Template Gallery** - The database for all CodeWords templates, including templates built by members in our community.&#x20;

**Workflow Logs** - Detailed records of what happened during workflow execution, useful for debugging issues. You can ask Cody to 'check the logs' if a workflow has failed to debug the issue.

**Web Agent** - An AI-powered browser automation that can perform complex web tasks by understanding and interacting with websites like a human would. You'll be able to see when this is active from within the platform.&#x20;

***

### Service structure and development

**Secrets** - Your unique API keys and credentials to workflows; these aren't exposed in logs or outputs. Please keep your unique secrets secure.&#x20;

**Correlation ID** - A unique tracking number that follows a request through multiple workflows, helping with debugging and monitoring.

**Implementation ID** - A unique identifier for each version of your workflow, allowing you to rollback to previous versions if needed.

**Service ID** - The permanent identifier for your workflow that stays the same across all versions and updates.

### Integrations and external services

**Native Integrations** - Direct connections built into the CodeWords platform for services like Slack, WhatsApp, and Google Drive that work seamlessly without additional setup.

**External Integrations** - Access to over 2000 external services (like Gmail, GitHub, HubSpot) through a unified integration system.

**Actions** - Operations your workflow can perform on external platforms, like "send an email," "create a document," or "post to social media."

**Triggers** - Event listeners that automatically start your workflow when something happens, like "new email received" or "file uploaded to Drive."

**CodeWords Chrome Extension** - Access more automation capability. You can download the CodeWords chrome extension [here](https://chromewebstore.google.com/detail/codewords/fgcbeegcaikofigbnfmmlgcimdkmfnce?hl=en), but you'll also be prompted within the platform.&#x20;

**Web Agent** - An AI-powered browser automation that can perform complex web tasks by understanding and interacting with websites like a human would.

### Workflow patterns

**Deep Research Pattern** - A multi-stage workflow that searches across multiple platforms, validates findings, and creates comprehensive reports.

**Monitoring Pattern** - Workflows that continuously watch for changes in websites, social media, or other data sources and notify you when something important happens.

**LinkedIn Automation Pattern** - Specialized workflows for interacting with LinkedIn while respecting rate limits and platform rules.

**Background Execution** - Running long workflows without blocking the user interface, allowing them to continue working while tasks complete.

**State Management** - How workflows remember information between runs and coordinate with other workflows.

**Redis State Management** - The system that temporarily stores data that workflows need to share or remember between executions.

### Templates and starting points

**Workflow Templates** - Pre-built, fully functional workflows you can use as-is or modify for your specific needs. These are packaged in our user interface so that each workflow template has its own run page where you can choose your inputs and actively run the automation.&#x20;

Available templates include:

* Brand Sentiment Analyzer - Monitors what people say about brands across social media
* LinkedIn Profile Enricher - Extracts detailed information from LinkedIn profiles
* Email AI Labeler - Automatically categorizes emails using artificial intelligence
* Website Monitor - Watches websites for changes and alerts you
* Person Finder - Discovers someone's online presence across multiple platforms

**Template Gallery** - The database for all CodeWords templates, including templates built by members in our community.&#x20;

### AI and LLM Integration

**Large Language Models (LLMs)** - AI systems like GPT, Claude, and Gemini that can understand and generate human-like text for processing and analyzing content.

**Anthropic Integration** - Access to Claude models (Opus, Sonnet, Haiku, Extended Thinking) for advanced reasoning and analysis.

**OpenAI Integration** - Access to GPT models (o3, GPT-5, GPT-4.1) for text analysis, content generation, and intelligent data processing.

**Gemini Integration** - Access to Google's AI models (2.5-pro, 2.5-flash) for text processing and analysis with vision capabilities.

**Structured Output** - AI responses formatted as organized data (like forms or tables) rather than just plain text.

**Tool Calling** - AI models that can use specific tools or functions to perform actions based on their analysis.

### User interface and access

**Auto-Generated UI** - The platform automatically creates user-friendly forms and interfaces based on your workflow's input requirements.

**CodeWords Default UI** - The built-in interface where users can run workflows by filling out forms and seeing results.

**Custom UI Generation** - Creating specialized interfaces for workflows when the default forms aren't sufficient.

**API Access** - Allowing external applications and systems to use your workflows programmatically.

**Field Descriptions** - Help text that appears in forms to guide users on what information to provide.

**Input Validation** - Automatic checking that ensures users provide the correct type and format of information.

**Response Models** - The structure that defines what results users will receive from workflows.

### Deployment and management

**Service Deployment** - The process of making your workflow live and available for use on the platform.

**Visibility Settings** - Controls for who can discover and use your workflows:

* Private - Only you can use it
* Public - Anyone on CodeWords can use it
* Template - Others can copy and modify it

**Service Validation** - Automatic checking to ensure workflows are properly configured before deployment.

**Request History** - Log of all the times your workflow has been run, with details about inputs and outputs.

**Workflow Logs** - Detailed records of what happened during workflow execution, useful for debugging issues. You can ask Cody to 'check the logs' if a workflow has failed to debug the issue.

**Version Control** - System for managing different versions of your workflows and rolling back changes if needed.

### Platform

**FastAPI Application** - The technical foundation that powers each workflow. Think of it as the "engine" that makes your automation work.

**Microservice** - A single-purpose automation workflow designed to do one specific task very well (like "extract LinkedIn profiles" or "send Slack messages").

**Sandbox Execution** - Each time a workflow runs, it gets its own secure, isolated environment that's created fresh and destroyed when finished. This ensures security and reliability.

**Serverless Execution** - Your workflows run automatically on-demand without you needing to manage any servers or technical infrastructure.

### Security and authentication

**API Key** - A secure token that identifies you and allows your workflows to access CodeWords services.

**OAuth Integration** - Secure method for connecting your workflows to external services like Google, Slack, or GitHub without sharing passwords.

**Rate Limiting** - Controls that prevent workflows from overwhelming external services with too many requests.
