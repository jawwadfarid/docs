# Notion

## Notion Actions in CodeWords

### Page Management Actions

#### 1. create-page

**What it does:** Creates a new page in a Notion workspace or database.&#x20;

**When to use it:** Perfect for automated documentation, project tracking, or content generation workflows.

#### 2. create-page-from-database

**What it does:** Creates a new database entry/page from a Notion database template.&#x20;

**When to use it:** Ideal for CRM automation, task creation, or structured data entry workflows.

#### 3. update-page

**What it does:** Modifies content, properties, or metadata of an existing Notion page.&#x20;

**When to use it:** Essential for keeping documentation current or updating project status automatically.

#### 4. duplicate-page

**What it does:** Creates an exact copy of an existing Notion page.&#x20;

**When to use it:** Great for templating workflows, backup creation, or project initialization.

#### 5. retrieve-page

**What it does:** Fetches complete details about a specific Notion page.&#x20;

**When to use it:** Perfect for data extraction, content analysis, or integration with other systems.

#### 6. find-page

**What it does:** Locates a specific Notion page by title or other identifiers.&#x20;

**When to use it:** Essential for page lookup operations or verifying page existence.

### Database Management Actions

#### 7. create-database

**What it does:** Creates a new Notion database with specified properties and structure.&#x20;

**When to use it:** Use when dynamically setting up project databases or organizing new data collections.

#### 8. update-database

**What it does:** Updates database properties, structure, or metadata.&#x20;

**When to use it:** Ideal for evolving data schemas or maintaining database organization.

#### 9. query-database

**What it does:** Searches and filters Notion database entries based on specified criteria.&#x20;

**When to use it:** Essential for data analysis, reporting, or finding specific records programmatically.

#### 10. retrieve-database-content

**What it does:** Gets all entries and data from a specified Notion database.&#x20;

**When to use it:** Ideal for data synchronization, reporting, or bulk operations.

#### 11. retrieve-database-schema

**What it does:** Fetches the structure and property definitions of a Notion database.&#x20;

**When to use it:** Use for dynamic form generation or understanding database structure programmatically.

### Content Management Actions

#### 12. update-block

**What it does:** Modifies specific content blocks within a Notion page.&#x20;

**When to use it:** Use for precise content updates or automated text/media replacements.

#### 13. append-block

**What it does:** Adds new content blocks to the end of a Notion page.&#x20;

**When to use it:** Perfect for logging activities, adding updates, or building progressive documentation.

#### 14. delete-block

**What it does:** Removes specific content blocks from a Notion page.&#x20;

**When to use it:** Useful for content cleanup, removing outdated information, or automated maintenance.

#### 15. retrieve-block

**What it does:** Gets details about a specific content block within a Notion page.&#x20;

**When to use it:** Perfect for targeted content analysis or block-level operations.

#### 16. create-comment

**What it does:** Adds a comment to a specific Notion page or database entry.&#x20;

**When to use it:** Perfect for automated feedback, status updates, or collaboration workflows.

### Data Retrieval Actions

#### 17. retrieve-page-property-item

**What it does:** Fetches the value of a specific property from a Notion page.&#x20;

**When to use it:** Useful for extracting specific data points for calculations or comparisons.

#### 18. search

**What it does:** Performs a full-text search across your Notion workspace.&#x20;

**When to use it:** Perfect for finding content, pages, or databases that match specific criteria.

### User Management Actions

#### 19. list-all-users

**What it does:** Retrieves a list of all users in the Notion workspace.&#x20;

**When to use it:** Ideal for user management, permission auditing, or team analytics.

#### 20. retrieve-user

**What it does:** Gets detailed information about a specific Notion user.&#x20;

**When to use it:** Perfect for user verification, profile management, or access control workflows.

### File Management Actions

#### 21. create-file-upload

**What it does:** Initiates a file upload process to Notion.&#x20;

**When to use it:** Use for adding documents, images, or media to Notion pages programmatically.

#### 22. send-file-upload

**What it does:** Uploads file content to Notion storage.&#x20;

**When to use it:** Essential for completing file attachment workflows or media automation.

#### 23. complete-file-upload

**What it does:** Finalizes the file upload process in Notion.&#x20;

**When to use it:** Required to complete multi-step file upload workflows.

#### 24. list-file-uploads

**What it does:** Lists all uploaded files in the Notion workspace.&#x20;

**When to use it:** Perfect for file management, storage auditing, or media organization.

#### 25. retrieve-file-upload

**What it does:** Gets details about a specific uploaded file in Notion.&#x20;

**When to use it:** Useful for file verification, metadata extraction, or download operations.

## Available Triggers in CodeWords

#### 1. new-page

**When it fires:** Triggers when a new page is created in your Notion workspace.&#x20;

**Business scenario:** Automate onboarding workflows, project initialization, or content approval processes.

#### 2. new-database

**When it fires:** Triggers when a new database is created in your workspace.&#x20;

**Business scenario:** Perfect for setting up automated database configurations or team notifications.

#### 3. updated-page

**When it fires:** Triggers when any page in your workspace is modified.&#x20;

**Business scenario:** Ideal for change tracking, approval workflows, or keeping external systems synchronized.

#### 4. updated-page-id

**When it fires:** Triggers when a specific page (by ID) is updated.&#x20;

**Business scenario:** Use for monitoring critical documents or triggering workflows for specific pages.

#### 5. updated-page-by-timestamp

**When it fires:** Triggers when pages are updated after a specific timestamp.&#x20;

**Business scenario:** Perfect for processing recent changes or building incremental sync workflows.

#### 6. page-or-subpage-updated

**When it fires:** Triggers when a page or any of its subpages are modified.&#x20;

**Business scenario:** Excellent for hierarchical content management or cascading update workflows.

#### 7. page-properties-updated-instant

**When it fires:** Triggers immediately when page properties change (real-time).&#x20;

**Business scenario:** Ideal for instant notifications, status change workflows, or real-time integrations.

#### 8. new-comment-created

**When it fires:** Triggers when someone adds a comment to any page in your workspace.&#x20;

**Business scenario:** Perfect for collaboration tracking, feedback workflows, or discussion notifications.

#### 9. new-webhook-event-instant

**When it fires:** Triggers on any Notion webhook event with instant delivery.&#x20;

**Business scenario:** Use for comprehensive real-time monitoring or custom event handling workflows.

## Building Practical Workflows with CodeWords

### Example workflow: Automated project management

**Trigger:** new-page — Fires when a new page is created in your project's database.

&#x20;**Action:** create-page — Automatically sets up task tracking pages for the new project.

&#x20;**Action:** append-block — Adds project template content and initial structure.&#x20;

**Action:** create-comment — Posts assignment notifications to relevant team members.

### Example workflow: Dynamic documentation system

**Trigger:** updated-page — Reacts to content changes across your workspace.&#x20;

**Action:** duplicate-page — Creates version control copies of important documents.&#x20;

**Action:** update-page — Adds revision timestamps and change tracking metadata.

&#x20;**Action:** create-comment — Notifies stakeholders about significant content updates.

### Example workflow: CRM integration workflow

**Trigger:** new-page — Activates when new contacts are added to your database.&#x20;

**Action:** query-database — Searches for related records and existing connections.&#x20;

**Action:** update-page — Enriches contact profiles with additional data points.&#x20;

**Action:** create-page-from-database — Generates follow-up tasks and action items automatically.

### Example workflow: Content approval pipeline

**Trigger:** page-properties-updated-instant — Fires immediately when content status changes.&#x20;

**Action:** retrieve-page — Analyzes content for approval criteria and compliance.&#x20;

**Action:** append-block — Adds review comments and feedback directly to the page.&#x20;

**Action:** update-page — Progresses content through defined approval stages.

## Practical Tips and What to Watch Out For

**Structure with databases:** Use create-database and query-database to organize information systematically. Well-structured databases enable powerful automation and reporting capabilities.

**Be proactive with updates:** Implement updated-page and property-specific triggers to maintain data consistency across your workspace and external systems.

**Leverage rich content:** Use append-block and update-block to create dynamic, living documents that evolve with your business needs and grow organically.

**Monitor collaboration:** Utilize new-comment-created and user-related actions to track team engagement and automate collaborative workflows effectively.

**File management:** Take advantage of the file upload actions to automate document attachment and media management within your Notion workspace seamlessly.
