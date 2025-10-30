# Slack

## Slack actions in CodeWords

Here's a comprehensive guide to all the actions you can perform with Slack in CodeWords, designed to streamline your team communication and enhance workplace collaboration.

### Available actions

1. upload-file

**What it does:** Uploads a file to a channel or direct message.

**When to use it:** To share documents, images, or files with your team instantly.

2. find-message

**What it does:** Searches for a specific message in a channel.

**When to use it:** To quickly locate important conversation threads or reference past discussions.

3. update-profile

**What it does:** Updates a user's profile information.

**When to use it:** To keep team member contact details current and accurate.

4. update-message

**What it does:** Edits a previously sent message.

**When to use it:** To correct typos or add information to a message without losing context.

5. update-group-members

**What it does:** Modifies group membership.

**When to use it:** To manage team member participation in group chats and private discussions.

6. set-status

**What it does:** Sets a user's Slack status.

**When to use it:** To inform your team of your current availability or activity automatically.

7. set-channel-topic

**What it does:** Sets the topic of a Slack channel.

**When to use it:** To communicate the focus or purpose of a channel clearly.

8. set-channel-description

**What it does:** Updates the channel's description.

**When to use it:** To provide more context about channel activities and guidelines.

9. send-message

**What it does:** Sends a message to a channel or user.

**When to use it:** For direct communication or general announcements.

10. send-message-to-user-or-group

**What it does:** Sends a message to a specific user or group.

**When to use it:** For targeted communication within the team or specific departments.

11. send-message-to-channel

**What it does:** Posts a message in a specific channel.

**When to use it:** To broadcast information to all channel members simultaneously.

12. send-message-advanced

**What it does:** Sends a message with advanced formatting options.

**When to use it:** For messages that require special formatting, links, or attachments.

13. send-large-message

**What it does:** Sends an extended message that exceeds typical limits.

**When to use it:** For detailed updates, reports, or comprehensive announcements.

14. send-block-kit-message

**What it does:** Sends a message using Slack's Block Kit for rich formatting.

**When to use it:** To create interactive and visually appealing messages with buttons or forms.

15. reply-to-a-message

**What it does:** Replies to a specific message in a thread.

**When to use it:** To maintain context in ongoing conversations and keep discussions organized.

16. list-users

**What it does:** Retrieves a list of all users in the Slack workspace.

**When to use it:** To manage users, perform audits, or analyze team composition.

17. list-replies

**What it does:** Lists replies to a specific message.

**When to use it:** To review conversations and follow-ups in message threads.

18. list-members-in-channel

**What it does:** Lists all members of a specific channel.

**When to use it:** To assess channel participation and engagement levels.

19. list-group-members

**What it does:** Lists members of a private group.

**When to use it:** For private group management and organization oversight.

20. list-files

**What it does:** Lists all files shared in the workspace.

**When to use it:** To manage and organize shared documents and media files.

21. list-channels

**What it does:** Lists all channels in the workspace.

**When to use it:** To navigate or restructure workspace channels effectively.

22. kick-user

**What it does:** Removes a user from a channel.

**When to use it:** To maintain group integrity or address security concerns.

23. invite-user-to-channel

**What it does:** Invites a user to join a channel.

**When to use it:** To include new members in relevant discussions and projects.

24. get-file

**What it does:** Retrieves a specific file from Slack.

**When to use it:** To access shared files for reference, download, or processing.

25. find-user-by-email

**What it does:** Locates a user in Slack using their email address.

**When to use it:** To quickly find and connect with team members across large workspaces.

26. delete-message

**What it does:** Deletes a specific message.

**When to use it:** To remove outdated or incorrect information from channels.

27. delete-file

**What it does:** Removes a file from Slack.

**When to use it:** To clear outdated files or manage storage efficiently.

28. create-reminder

**What it does:** Sets a reminder for yourself or others.

**When to use it:** To ensure important tasks or deadlines are not forgotten.

29. create-channel

**What it does:** Creates a new Slack channel.

**When to use it:** To organize discussions by project, topic, or team structure.

30. archive-channel

**What it does:** Archives a channel that's no longer active.

**When to use it:** To declutter your Slack workspace while preserving conversation history.

31. approve-workflow

**What it does:** Approves a pending workflow request.

**When to use it:** For workflow management and task approval processes.

32. add-emoji-reaction

**What it does:** Adds an emoji reaction to a message.

**When to use it:** To provide quick feedback, acknowledgment, or express sentiment.

### Available Slack triggers

1. new-user-mention

**When it fires:** When a user is mentioned in a message.

**Business scenario:** Automatically notify users of important mentions or escalate urgent requests.

2. new-user-added

**When it fires:** When a new user joins the workspace.

**Business scenario:** Trigger onboarding workflows and welcome processes for new team members.

3. new-saved-message

**When it fires:** When a message is saved by a user.

**Business scenario:** Track important information that team members are bookmarking for reference.

4. new-reaction-added

**When it fires:** When a reaction is added to a message.

**Business scenario:** Monitor team engagement and sentiment on announcements or updates.

5. new-message-in-channels

**When it fires:** When a new message is posted in a channel.

**Business scenario:** Route messages to appropriate teams or systems based on channel activity.

6. new-keyword-mention

**When it fires:** When a specific keyword is mentioned in a message.

**Business scenario:** Alert relevant teams when critical topics like "outage" or "security" are discussed.

7. new-interaction-event-received

**When it fires:** When a user interacts with an app feature.

**Business scenario:** Track app usage and user engagement with custom integrations.

8. new-direct-message

**When it fires:** When a new direct message is received.

**Business scenario:** Route direct messages to support systems or escalate urgent communications.

9. new-channel-created

**When it fires:** When a new channel is created in the workspace.

**Business scenario:** Automatically set up channel templates, permissions, or notifications for new projects.

### Building practical workflows

Let's explore how you can bring these actions and triggers together to create seamless workflows.

#### Example workflow 1: Welcome new team members

* **Trigger:** new-user-added
* **Action:** send-message — Send a welcome message to the new user in a designated channel
* **Action:** create-reminder — Set a reminder for HR to follow up with onboarding materials

#### Example workflow 2: Automated file management

* **Trigger:** new-saved-message
* **Action:** list-files — List all files in the workspace to assess storage usage
* **Action:** delete-file — Remove outdated files based on predefined conditions

#### Example workflow 3: Keyword alert system

* **Trigger:** new-keyword-mention
* **Action:** find-user-by-email — Locate the appropriate team lead
* **Action:** send-message-to-user-or-group — Alert the relevant team about critical mentions

### Practical tips

**Start simple:** Begin with basic workflows and gradually incorporate more complex automations as your team becomes comfortable with the system.

**Iterate and improve:** Regularly review and refine your workflows to ensure they're meeting your business needs and adapting to team changes.

**Communicate clearly:** Use clear and descriptive names for workflows and actions to keep everything organized and maintainable.

**Monitor and adapt:** Keep an eye on usage and effectiveness, and be ready to adjust workflows as your business and team dynamics evolve.
