# Gmail

### Gmail actions in CodeWords

Here's a comprehensive guide to all the actions you can perform with Gmail in CodeWords

1. list-send-as-aliases

**What it does:** Retrieves a list of all email aliases that can be used to send emails.

**When to use it:** Perfect for businesses with multiple brands or departments, allowing you to ensure emails are sent from the correct alias.

2. get-send-as-alias

**What it does:** Retrieves details of a specific send-as alias.

**When to use it:** Use this when you need to verify or update settings for a specific email alias in your organization.

3. delete-email

**What it does:** Permanently deletes an email from your Gmail account.

**When to use it:** Useful for maintaining inbox hygiene by automatically removing unwanted emails.

4. download-attachment

**What it does:** Downloads attachments from an email and saves them to a specified location.

**When to use it:** Ideal for businesses needing to save and organize documents received via email.

5. update-primary-signature

**What it does:** Updates the primary email signature for the user.

**When to use it:** Ideal for updating branding or contact details across all outgoing emails.

6. update-org-signature

**What it does:** Updates the organizational signature used for all users.

**When to use it:** Use when there's a company-wide update to email signatures for consistency.

7. send-email

**What it does:** Sends an email from your Gmail account.

**When to use it:** Perfect for automated responses, newsletters, or routine communication tasks.

8. remove-label-from-email

**What it does:** Removes a specific label from an email.

**When to use it:** Use this to tidy up your labeling system by removing outdated or incorrect labels.

9. list-labels

**What it does:** Lists all labels available in the Gmail account.

**When to use it:** Useful for getting an overview of all existing labels to better organize your emails.

10. find-email

**What it does:** Searches for emails based on specified criteria.

**When to use it:** Ideal for locating specific emails that meet certain conditions, like sender or subject.

11. create-draft

**What it does:** Creates a draft email with specified content.

**When to use it:** Great for preparing emails that require review before sending.

12. archive-email

**What it does:** Moves emails to the archive.

**When to use it:** Use it to declutter your inbox while keeping emails accessible for future reference.

13. approve-workflow

**What it does:** Approves a specified workflow step.

**When to use it:** Perfect for businesses with approval processes integrated into email communication.

14. add-label-to-email

**What it does:** Adds a specified label to an email.

**When to use it:** Use it to categorize emails for better organization and retrieval.

15. create-label

**What it does:** Creates a new label in the Gmail account.

**When to use it:** Ideal for setting up new organizational structures or categories within your inbox.

### Available Gmail triggers

1. new-sent-email

**When it fires:** Triggers when a new email is sent from your Gmail account.

**Business scenario:** Automate follow-up actions, like logging sent emails in a CRM.

2. new-labeled-email

**When it fires:** Triggers when a new email is labeled with a specified label.

**Business scenario:** Ideal for initiating workflows based on categorized emails, such as forwarding to a specific department.

3. new-email-received

**When it fires:** Triggers when a new email arrives in your inbox.

**Business scenario:** Use to automate immediate responses or notifications for incoming emails.

4. new-email-matching-search

**When it fires:** Triggers when an email matching specific search criteria is received.

**Business scenario:** Automatically process or flag important emails that meet set criteria.

5. new-attachment-received

**When it fires:** Triggers when an email with an attachment is received.

**Business scenario:** Automatically download and save attachments for record-keeping or review.

### Building practical workflows

Let's explore how you can bring these actions and triggers together to create seamless workflows.

#### Automated client onboarding

Connect **new-email-received** to search for emails with "Welcome" in the subject.&#x20;

Then, use **download-attachment** to save onboarding documents, and **send-email** to notify your team of new clients.

#### Signature update launch

Use **update-org-signature** to roll out new email signatures company-wide. Combine with **send-email** to inform your team about the update and its benefits.

Schedule **find-email** to search for emails containing weekly report attachments, then use **download-attachment** and **send-email** to distribute them to stakeholders.

### Practical tips

**Organize with labels:** Use **add-label-to-email** and **list-labels** to keep your inbox tidy and efficient. Labeling helps in easy retrieval and categorization.

**Be proactive with triggers:** Implement **new-email-received** and **new-attachment-received** to stay on top of important communications and documents without manual checks.

**Draft wisely:** Use **create-draft** for emails requiring approval or further input, ensuring your communication is polished and accurate.
