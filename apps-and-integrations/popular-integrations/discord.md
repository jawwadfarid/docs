# Discord

### Discord Actions in CodeWords

Here's a comprehensive list of all the actions you can perform with Discord

#### Messaging Actions

1. send-message

**What it does:** Sends a text message to a specified Discord channel.&#x20;

**When to use it:** Perfect for automated notifications, alerts, or routine communication to Discord servers.

2. send-message-with-file

**What it does:** Sends a message to Discord that includes a file attachment.&#x20;

**When to use it:** Ideal for sharing reports, images, documents, or data files with your Discord community.

3. send-message-advanced

**What it does:** Sends advanced Discord messages with embeds, buttons, and rich formatting.&#x20;

**When to use it:** Use when you need to create professional-looking messages with interactive elements or rich media.

4. send-message-to-forum-post

**What it does:** Posts a message to a specific Discord forum thread.&#x20;

**When to use it:** Perfect for automated responses to forum discussions or adding context to community threads.

4. send-message-to-forum-post

**What it does:** Adds an emoji reaction to a specific Discord message.&#x20;

**When to use it:** Useful for automated feedback, approval workflows, or engagement tracking.

#### Channel Management Actions

6. create-guild-channel

**What it does:** Creates a new channel in a Discord server.&#x20;

**When to use it:** Ideal for dynamically organizing discussions or creating temporary project channels.

7. rename-channel

**What it does:** Changes the name of an existing Discord channel.&#x20;

**When to use it:** Perfect for updating channel purposes or reflecting current projects or status.

8. modify-channel

**What it does:** Updates channel settings like permissions, topic, or category.&#x20;

**When to use it:** Use for automated channel management or permission updates based on events.

9. delete-channel

**What it does:** Permanently removes a Discord channel from the server.&#x20;

**When to use it:** Useful for cleaning up temporary channels or automated server maintenance.

10. create-channel-invite

**What it does:** Generates an invitation link for a Discord channel.&#x20;

**When to use it:** Perfect for automated onboarding or sharing access to specific channels.

11. list-channels

**What it does:** Retrieves a list of all channels in a Discord server.&#x20;

**When to use it:** Useful for server management workflows or building channel selection interfaces.

### Member Management Actions

12. modify-guild-member

**What it does:** Updates a guild member's roles, nickname, or other properties.&#x20;

**When to use it:** Ideal for automated role management or member status updates.

13. add-role

**What it does:** Assigns a role to a Discord server member.&#x20;

**When to use it:** Perfect for automated role assignments based on behavior, payments, or achievements.

14. remove-user-role

**What it does:** Removes a specific role from a Discord server member.&#x20;

**When to use it:** Use for automated role removal, subscription expiration, or disciplinary actions.

15. change-nickname

**What it does:** Updates a member's display name in the Discord server.&#x20;

**When to use it:** Useful for automated name formatting or status indicators in usernames.

16. list-guild-members

**What it does:** Retrieves a list of all members in a Discord server.&#x20;

**When to use it:** Ideal for member analytics, bulk operations, or community management tasks.

### Data Retrieval Actions

17. get-message

**What it does:** Retrieves details about a specific Discord message.&#x20;

**When to use it:** Perfect for message analysis, content moderation, or audit trails.

18. list-channel-messages

**What it does:** Fetches messages from a Discord channel with optional filtering.&#x20;

**When to use it:** Useful for content analysis, backup creation, or message processing workflows.

19. delete-message

**What it does:** Removes a specific message from a Discord channel.&#x20;

**When to use it:** Essential for automated moderation or content cleanup workflows.

20. find-user

**What it does:** Searches for a Discord user by username or ID.&#x20;

**When to use it:** Perfect for user verification, lookup operations, or member management.

21. find-channel

**What it does:** Locates a Discord channel by name or ID.&#x20;

**When to use it:** Useful for dynamic channel operations or automated channel management.

22. list-channel-invites

**What it does:** Lists all active invitation links for a specific channel.&#x20;

**When to use it:** Helpful for invite management, security audits, or access control.

23. list-users-with-emoji-reactions

**What it does:** Gets all users who reacted to a message with a specific emoji.&#x20;

**When to use it:** Perfect for polls, engagement tracking, or event participation management.

### Available Triggers in CodeWords

1. new-message

**When it fires:** Triggers when a new message is posted in monitored Discord channels.&#x20;

**Business scenario:** Automate responses to customer questions, log important discussions, or trigger workflows based on message content.

2. reaction-added

**When it fires:** Triggers when someone adds an emoji reaction to a Discord message.&#x20;

**Business scenario:** Perfect for approval workflows, voting systems, or engagement-based automations.

3. new-guild-member

**When it fires:** Triggers when a new member joins your Discord server.&#x20;

**Business scenario:** Ideal for automated welcome messages, role assignments, or onboarding workflows.

4. new-command-received

**When it fires:** Triggers when a Discord slash command is used in your server.

**Business scenario:** Use for custom bot commands, automated help systems, or interactive server management.

5. message-deleted

**When it fires:** Triggers when a message is deleted from monitored channels.&#x20;

**Business scenario:** Essential for moderation logging, audit trails, or content backup systems.

### Building Practical Workflows with CodeWords

#### Example workflow 1: Automated community management

**Trigger:** new-guild-member — Fires when new members join your Discord server.&#x20;

**Action:** add-role — Assigns welcome roles to new members automatically.&#x20;

**Action:** send-message — Posts a personalized greeting in the welcome channel.&#x20;

**Action:** create-guild-channel — Creates a temporary introduction channel for new members.

#### Example workflow 2: Smart moderation system

**Trigger:** new-message — Reacts to messages posted in monitored channels.&#x20;

**Action:** delete-message — Removes messages that violate community guidelines.&#x20;

**Action:** send-message-advanced — Notifies moderators with detailed violation reports using rich embeds.&#x20;

**Action:** modify-guild-member — Updates member status or applies temporary restrictions.

#### Example workflow 3: Interactive feedback collection

**Trigger:** reaction-added — Activates when users react to feedback posts with specific emojis.&#x20;

**Action:** list-users-with-emoji-reactions — Collects all users who participated in the feedback.&#x20;

**Action:** send-message-advanced — Shares feedback summaries with interactive elements and rich formatting.

### Practical Tips and What to Watch Out For

**Organize with channels:** Use create-guild-channel and modify-channel to keep your server organized and purposeful. Dynamic channel creation helps manage growing communities effectively.

**Be proactive with member management:** Implement new-guild-member and role-based triggers to automate onboarding, reducing manual work while ensuring consistent member experiences.

**Leverage rich messaging:** Use send-message-advanced for professional-looking notifications with embeds and interactive elements that engage your community effectively.

**Monitor engagement:** Utilize reaction-based triggers and message monitoring to understand community engagement and automate responses to popular content.
