# Slack



1.  **upload-file**: Uploads a file to a channel or direct message.

    When to use it: To share documents, images, or files with your team instantly.
2.  **find-message**: Searches for a specific message in a channel.

    When to use it: To quickly locate important conversation threads.
3.  **update-profile**: Updates a user's profile information.

    When to use it: To keep team member contact details current.
4.  **update-message**: Edits a previously sent message.

    When to use it: To correct typos or add information to a message.
5.  **update-group-members**: Modifies group membership.

    When to use it: To manage team member participation in group chats.
6.  **set-status**: Sets a user's Slack status.

    When to use it: To inform your team of your current availability or activity.
7.  **set-channel-topic**: Sets the topic of a Slack channel.&#x20;

    When to use it: To communicate the focus or purpose of a channel.
8.  **set-channel-description**: Updates the channel's description.

    When to use it: To provide more context about channel activities.
9.  **send-message**: Sends a message to a channel or user.

    When to use it: For direct communication or announcements.
10. **send-message-to-user-or-group**: Sends a message to a specific user or group.

    When to use it: For targeted communication within the team.
11. **send-message-to-channel**: Posts a message in a specific channel.

    When to use it: To broadcast information to all channel members.
12. **send-message-advanced**: Sends a message with advanced formatting options. When to use it: For messages that require special formatting or attachments.
13. **send-large-message**: Sends an extended message that exceeds typical limits.

    When to use it: For detailed updates or reports.
14. **send-block-kit-message**: Sends a message using Slack's Block Kit for rich formatting.

    When to use it: To create interactive and visually appealing messages.
15. **reply-to-a-message:** Replies to a specific message in a thread.

    When to use it: To maintain context in ongoing conversations.
16. **list-users:** Retrieves a list of all users in the Slack workspace.

    When to use it: To manage users or perform audits.
17. **list-replies:** Lists replies to a specific message.

    When to use it: To review conversations and follow-ups.
18. **list-members-in-channel:** Lists all members of a specific channel.

    When to use it: To assess channel participation and engagement.
19. **list-group-members:** Lists members of a private group.

    When to use it: For private group management and organization.
20. **list-files:** Lists all files shared in the workspace.

    When to use it: To manage and organize shared documents and media.
21. **list-channels:** Lists all channels in the workspace.

    When to use it: To navigate or restructure workspace channels.
22. kick-user: Removes a user from a channel.

    When to use it: To maintain group integrity or security.
23. **invite-user-to-channel:** Invites a user to join a channel.

    When to use it: To include new members in relevant discussions.
24. **get-file:** Retrieves a specific file from Slack.

    When to use it: To access shared files for reference or use.
25. **find-user-by-email:** Locates a user in Slack using their email address.

    When to use it: To quickly find and connect with team members.
26. **delete-message:** Deletes a specific message.

    When to use it: To remove outdated or incorrect information.
27. **delete-file:** Removes a file from Slack.

    When to use it: To clear outdated files or manage storage.
28. **create-reminder:** Sets a reminder for yourself or others.&#x20;

    When to use it: To ensure important tasks are not forgotten.
29. **create-channel:** Creates a new Slack channel.

    When to use it: To organize discussions by project or topic.
30. **archive-channel:** Archives a channel that's no longer active.

    When to use it: To declutter your Slack workspace.
31. **approve-workflow:** Approves a pending workflow request.

    When to use it: For workflow management and task approval processes.
32. **add-emoji-reaction:** Adds an emoji reaction to a message.

    When to use it: To provide quick feedback or acknowledgment.

### Slack triggers <a href="#slack-triggers" id="slack-triggers"></a>

1. **new-user-mention** When it fires: When a user is mentioned in a message.&#x20;
2. **new-user-added** When it fires: When a new user joins the workspace.
3. **new-saved-message** When it fires: When a message is saved by a user.
4. **new-reaction-added** When it fires: When a reaction is added to a message.
5. **new-message-in-channels** When it fires: When a new message is posted in a channel.
6. **new-keyword-mention** When it fires: When a specific keyword is mentioned in a message.
7. **new-interaction-event-received** When it fires: When a user interacts with an app feature.Business scenario: Tracking app usage and user engagement.
8. **new-direct-message** When it fires: When a new direct message is received.
9. **new-channel-created** When it fires: When a new channel is created in the workspace.

### Building practical workflows <a href="#building-practical-workflows" id="building-practical-workflows"></a>

#### Example workflow 1: Welcome new team members <a href="#example-workflow-1-welcome-new-team-members" id="example-workflow-1-welcome-new-team-members"></a>

1. **Trigger**: new-user-added
2. **Action**: send-message - Send a welcome message to the new user in a designated channel.
3. **Action**: create-reminder - Set a reminder for HR to follow up with onboarding materials.

#### Example workflow 2: File management <a href="#example-workflow-2-file-management" id="example-workflow-2-file-management"></a>

1. **Trigger**: new-saved-message
2. **Action**: list-files - List all files in the workspace.
3. **Action**: delete-file - Remove outdated files based on conditions.

### Practical tips <a href="#practical-tips" id="practical-tips"></a>

* **Start simple**: Begin with basic workflows and gradually incorporate more complex automations.
* **Iterate and improve**: Regularly review and refine your workflows to ensure they're meeting your business needs.
* **Communicate clearly**: Use clear and descriptive names for workflows and actions to keep everything organized.
* **Monitor and adapt**: Keep an eye on usage and effectiveness, and be ready to adjust as your business evolves.
