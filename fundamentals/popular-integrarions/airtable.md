# Airtable

## Airtable actions in CodeWords

#### 1. create-single-record

* **What it does**: Adds a single new record to a specified table.
* **When to use it**: Use this when you need to add individual entries, like a new customer in your CRM.

#### 2. create-multiple-records

* **What it does**: Adds several new records at once.
* **When to use it**: Perfect for bulk data imports, like uploading a batch of new leads from a trade show.

#### 3. create-table

* **What it does**: Sets up a new table within a base.
* **When to use it**: Ideal for expanding your database with new categories of information, like adding a table for customer feedback.

#### 4. create-field

* **What it does**: Adds a new field (column) to a table.
* **When to use it**: Use this when you need to track additional data points, such as a new sales metric.

#### 5. create-comment

* **What it does**: Adds a comment to a record.
* **When to use it**: Great for leaving notes or updates on specific records, like a project status update.

#### 6. update-record

* **What it does**: Modifies an existing record with new data.
* **When to use it**: Use this to update customer details or amend order statuses.

#### 7. update-table

* **What it does**: Changes settings at the table level.
* **When to use it**: Useful for adjusting table configurations, like changing permissions.

#### 8. update-field

* **What it does**: Modifies a field in a table.
* **When to use it**: Handy for renaming fields or changing field types.

#### 9. update-comment

* **What it does**: Edits an existing comment on a record.
* **When to use it**: Ideal for revising notes or clarifying previous comments.

#### 10. delete-record: Removes a record from a table.

* **When to use it**: Use this carefully to clean up obsolete data, like removing outdated contacts.

#### 11. get-record

* **What it does**: Retrieves a specific record based on a given ID.
* **When to use it**: Perfect for fetching detailed information about a customer or order.

#### 12. get-record-or-create

* **What it does**: Retrieves a record or creates it if it doesn’t exist.
* **When to use it**: Useful for ensuring data consistency, like checking for duplicate entries before adding new ones.

#### 13. list-records

* **What it does**: Lists all records in a table.
* **When to use it**: Ideal for generating reports or exporting data.

#### 14. list-records-in-view

* **What it does**: Lists records from a specific view.
* **When to use it**: Use this to filter data according to specific criteria, like a sales pipeline.

#### 15. list-tables

* **What it does**: Lists all tables within a base.
* **When to use it**: Useful for getting an overview of your database structure.

#### 16. list-bases

* **What it does**: Lists all bases in your Airtable workspace.
* **When to use it**: Perfect for navigating through multiple projects.

#### 17. search-records

* **What it does**: Finds records that match a search query.
* **When to use it**: Ideal for locating specific data points, like finding all customers from a particular region.

#### 18. create-or-update-record

* **What it does**: Creates a new record or updates an existing one if it matches certain criteria.
* **When to use it**: Great for maintaining up-to-date information, like syncing customer profiles.

## &#x20;Available Triggers in CodeWords

#### 1. new-records

* **When it fires**: Triggers when new records are added.
* **Business scenario**: Automatically send a welcome email to new customers.

#### 2. new-records-in-view

* **When it fires**: Triggers when new records appear in a specific view.
* **Business scenario**: Notify the sales team when new leads enter the "Qualified" view.

#### 3. new-or-modified-records

* **When it fires**: Triggers when records are created or modified.
* **Business scenario**: Update your team chat with changes to active projects.

#### 4. new-or-modified-records-in-view

* **When it fires**: Triggers on new or modified records in a view.
* **Business scenario**: Alert managers to significant changes in high-priority projects.

#### 5. new-or-modified-field

* **When it fires**: Triggers when a field is added or changed.
* **Business scenario**: Keep track of structural database changes for audit purposes.

#### 6. new-field

* **When it fires**: Triggers when a new field is created.
* **Business scenario**: Notify stakeholders when new metrics are being tracked.

#### 7. new-modified-or-deleted-records

* **When it fires**: Triggers on any record addition, change, or deletion.
* **Business scenario**: Maintain a comprehensive change log for compliance.

#### 8. new-modified-or-deleted-records-instant

* **When it fires**: Instantly triggers on any record addition, change, or deletion.
* **Business scenario**: Immediately update dashboards or reports with real-time data changes.

## Building practical workflows with CodeWords

### Example workflow: Automating lead management

1. **Trigger**: `new-records-in-view` — Fires when new leads enter the "Potential" view in Airtable.
2. **Action**: `create-single-record` — Adds these leads to your CRM database as individual records.
3. **Action**: `create-comment` — Leaves a note on each record indicating the source of the lead.
4. **Action**: `update-record` — Updates the lead status to "Contacted" once a follow-up email is sent.

### Example workflow: Real-time project tracking

1. **Trigger**: `new-modified-or-deleted-records-instant` — Instantly reacts to changes in project records.
2. **Action**: `list-records-in-view` — Retrieves all current tasks from the "In Progress" view.
3. **Action**: `create-or-update-record` — Updates a project management tool with the latest task status.

## Practical tips and what to watch out for

* **Consistency is key**: Use `get-record-or-create` to avoid duplicates and maintain clean data.
* **Plan your views**: Make use of specific views to filter data appropriately and trigger the right automations.
* **Stay informed**: Use triggers like `new-modified-or-deleted-records` to keep everyone updated on important changes.
