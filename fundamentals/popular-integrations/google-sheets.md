# Google Sheets

## Google Sheets actions in CodeWords

Here's a comprehensive list of all the actions you can perform with Google Sheets automations:

1. **add-single-row**: Insert a new row with specific data. Perfect for adding a new lead to your CRM sheet.
2. **add-multiple-rows**: Add several rows at once. Useful for importing bulk data, like a list of new products.
3. **add-column**: Create a new column. Handy when expanding your spreadsheet to include new data points.
4. **update-row**: Modify data in an existing row. Great for updating a customer's contact information.
5. **update-multiple-rows**: Change data across multiple rows simultaneously. Ideal for revising product prices.
6. **update-cell**: Change the value in a specific cell. Use it to correct a typo in your sales figures.
7. **upsert-row**: Update a row if it exists, or insert it if it doesn't. Perfect for managing inventory levels.
8. **find-row**: Locate a row based on criteria. Use it to search for a specific order in your sales sheet.
9. **get-values-in-range**: Retrieve data from a specific range. Useful for generating reports.
10. **get-cell**: Access the value in a specific cell. Handy when a particular data point is needed.
11. **get-spreadsheet-by-id**: Access a spreadsheet using its ID. Ideal for working with multiple spreadsheets.
12. **list-worksheets**: Display all worksheets within a spreadsheet. Useful for navigation and organization.
13. **create-spreadsheet**: Start a new spreadsheet from scratch. Perfect for launching new projects.
14. **create-worksheet**: Add a new worksheet to an existing spreadsheet. Great for expanding existing data sets.
15. **copy-worksheet**: Duplicate a worksheet. Ideal for creating templates or backups.
16. **delete-rows**: Remove unwanted rows. Useful for cleaning up outdated information.
17. **delete-worksheet**: Erase an entire worksheet. Perfect for decluttering.
18. **clear-rows**: Empty the contents of rows without deleting them. Great for resetting data for reuse.
19. **clear-cell**: Clear data from a specific cell. Handy for correcting errors.
20. **insert-comment**: Add a comment to a cell. Useful for leaving notes or instructions.
21. **insert-anchored-note**: Attach a note to a specific cell. Ideal for detailed explanations or reminders.

## Google Sheets triggers in CodeWords

Triggers are the events that set your workflows in motion. Here are all the triggers you can use with Google Sheets:

1. **new-records**: Fires when new rows are added. Use it to notify your sales team of new leads.
2. **new-records-in-view**: Triggers when new rows appear in a specific view. Handy for monitoring specific data sets.
3. **new-or-modified-records**: Activates on new or updated rows. Great for keeping track of changes in real-time.
4. **new-or-modified-records-in-view**: Fires for changes in a specific view. Useful for focused monitoring.
5. **new-or-modified-field**: Triggers when a specific field is altered. Ideal for tracking important changes.
6. **new-field**: Activates when a new field is added. Perfect for documenting expansions.
7. **new-modified-or-deleted-records**: Fires for any changes, additions, or deletions. Comprehensive tracking made easy.
8. **new-modified-or-deleted-records-instant**: Instantly triggers on any record changes. Real-time updates without delay.

## Real-world business scenarios

Let's explore how you can use these actions and triggers in practical workflows:

* **Sales tracking**: Use "add-single-row" to log new sales leads. Pair it with "new-records" to alert your sales team instantly.
* **Inventory management**: Combine "upsert-row" and "new-or-modified-records" to keep your inventory levels accurate and your supply chain smooth.
* **Project updates**: Use "update-multiple-rows" to adjust project timelines, and "new-or-modified-field" to notify stakeholders of any changes.

## Practical tips and what to watch out for

* **Keep it simple**: Start with basic automations and expand as you gain confidence.
* **Test your workflows**: Before deploying, test the automations to ensure they work as expected.
* **Backup data regularly**: While CodeWords is reliable, it's always good to have a backup of your critical data.
