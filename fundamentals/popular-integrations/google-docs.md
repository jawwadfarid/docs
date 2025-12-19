# Google Docs

### Google Docs actions in CodeWords

Here's a comprehensive guide to all the actions you can perform with Google Docs in CodeWords.

1. replace-text

**What it does:** Replaces specific text in a document.

**When to use it:** Use this action when you need to update recurring text in documents, like changing dates in contracts or updating placeholders with current information.

2. replace-image

**What it does:** Replaces an existing image in a document with a new one.

**When to use it:** Perfect for refreshing visual content in marketing materials or presentations without altering the document structure.

3. insert-text

**What it does:** Inserts text at a specified location in a document.

**When to use it:** Ideal for adding personalized messages or updates to templates, such as greeting cards or newsletters.

4. insert-table

**What it does:** Inserts a table at a specified location in a document.

**When to use it:** Use this when you need to present data clearly, like adding a pricing table to a proposal.

5. insert-page-break

**What it does:** Inserts a page break at a specified location in a document.

**When to use it:** Great for formatting long documents, ensuring each section starts on a new page.

6. get-tab-content

**What it does:** Retrieves content from a specified tab within a document.

**When to use it:** Handy for pulling specific parts of a document for review or sharing, such as extracting the agenda from meeting notes.

7. get-document

**What it does:** Retrieves the entire content of a document.

**When to use it:** Use this for archiving documents or when you need to analyze the complete text for insights.

8. find-document

**What it does:** Finds a document based on search criteria.

**When to use it:** Useful for locating specific files quickly, especially in large collections of documents.

9. create-document

**What it does:** Creates a new document.

**When to use it:** Perfect for generating new files for projects, reports, or any documentation needs.

10. create-document-from-template

**What it does:** Creates a document using a specified template.

**When to use it:** Streamline processes by using templates for standard documents like invoices or memos.

11. append-text

**What it does:** Appends text to the end of a document.

**When to use it:** Use this to add closing remarks or additional information without altering the core content.

12. append-image

**What it does:** Appends an image to the end of a document.

**When to use it:** Great for adding signatures or visual confirmations at the end of reports.

### Available Google Docs triggers

1. new-or-updated-document

**When it fires:** This trigger activates when a document is created or modified.

**Business scenario:** Use this to notify team members when important documents are updated, like changes in project plans.

2. new-document-created

**When it fires:** This trigger activates whenever a new document is created.

**Business scenario:** Automatically initiate review processes or notifications when new documents are added to your system.

### Building practical workflows

Let's explore how you can bring these actions and triggers together to create seamless workflows.

#### Example workflow 1: Automatic meeting summary

* **Trigger:** new-document-created
* **Actions:** get-document, insert-table, append-text
* **Workflow:** Whenever a new meeting notes document is created, retrieve its content, summarize it into a table format, and append additional notes or action items at the end.

#### Example workflow 2: Customer onboarding document

* **Trigger:** new-or-updated-document
* **Actions:** create-document-from-template, replace-text, replace-image
* **Workflow:** When a new customer onboarding document is updated, automatically generate a new document using a template, replace placeholders with customer-specific information, and update any branding images.

### Practical tips

**Optimize templates:** Use the **create-document-from-template** action to ensure consistency across your documents.

**Stay notified:** Set up triggers to keep your team informed of critical document changes.

**Security first:** Rest assured, CodeWords securely handles your Google Docs connections, keeping your data safe.

**Experiment with Cody:** Let our AI automation assistant suggest workflow improvements or new automations to enhance your productivity.

<br>
