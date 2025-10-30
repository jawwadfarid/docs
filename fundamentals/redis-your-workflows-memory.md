---
description: >-
  Learn how to use Redis as your workflow’s memory in CodeWords — store, recall,
  and manage data between runs to build smarter, faster, and more stateful
  automations.
icon: database
---

# Redis: Your Workflow’s Memory

### What Is Redis

**Redis** is what gives your workflow **memory**. It lets your automations remember information between workflow runs to make smarter decisions next time.

Without Redis, your workflow:

* Runs once, finishes its task, and forgets everything.
* Starts fresh each time, as if it’s never seen the data before.

With Redis, your workflow:

* Can save key details (like preferences, recent results, or progress).
* Picks up where it left off when it runs again.
* Feels smarter, faster, and more personal.

Think of it as your workflow’s short-term memory, it writes in while working.

### Why is Redis Useful?&#x20;

Redis allows workflows to store small pieces of information that make them stateful and smarter over time.

### Real-World Examples

* **Website Monitor:**\
  Detects if a page’s content changed since the last check.
* **Customer Notifications:**\
  Remembers who has already been notified, and avoids sending messages twice.
* **Report Generation:**\
  Saves previous data snapshots and only reports new updates.
* **Chatbot Memory:**\
  Keeps short-term context from a user conversation, so replies stay relevant.

When a workflow runs, Redis acts like a  memory it can write data in:

1. The workflow saves what it learns (“User prefers daily reports”).
2. The next time it runs, it looks back at that memory.
3. If the memory is outdated, Redis automatically removes it after some time.

It’s a simple but powerful way to make automations more personal and efficient — without needing a full database.

### Best Practices

* Use Redis when your workflow needs memory, like remembering settings or checking for new updates.
* Keep data small and focused as Redis is meant for quick notes, not large files.
* Let data expire automatically as short memories keep your automations fast and clean.
* Use it for context, not history it’s great for short-term recall, not long-term storage.

### When Not to Use Redis

* When you need to store data permanently (use a database instead).
* When your automation doesn’t need to remember anything.
* When the information is too large or sensitive to store temporarily.

### How Cody Decides When to Use Redis

You don’t need to worry about when or how to use Redis, Cody handles that automatically.\
When you describe your automation, Cody analyzes what your workflow needs:

* If your automation needs to remember data (like tracking changes or storing preferences), Cody will automatically add Redis.
* If your workflow doesn’t need memory, Cody skips Redis to keep things simpler and faster.

In short, Cody knows when memory is useful and uses Redis only when it actually improves your automation.

### FAQ

<details>

<summary>Do I need to set up Redis myself?</summary>

No. Redis is built into CodeWords. Cody manages all setup and connections automatically and you never have to install or maintain anything.

</details>

<details>

<summary>When does CodeWords use Redis?</summary>

Redis is used when your automation needs short-term memory for example, to remember preferences, cache results, or track changes between workflow runs.

</details>

<details>

<summary>Can Cody decide when Redis is needed?</summary>

Yes. Cody automatically detects when memory will make your automation smarter or more efficient and adds Redis support when appropriate.

</details>

<details>

<summary>Is my Redis data secure?</summary>

Absolutely. All Redis data is encrypted, isolated per user, and automatically deleted after its expiration period. Only your workflows can access it.

</details>

<details>

<summary>Is Redis required for every workflow?</summary>

No. Many simple or one-time automations don’t need Redis. It’s only used when memory adds real value to your workflow.

</details>

