# Reddit Weekly Slack Summary

<a href="https://codewords.agemo.ai/run/reddit_weekly_slack_summary" class="button primary">Use this template</a>

### Description

This automation monitors selected Reddit communities and turns the most relevant posts into a weekly Slack summary by combining Reddit discussions with AI technology into a clear, actionable digest. It first searches your chosen subreddits for recent posts that match your query, then converts those posts into a readable format and analyzes them with AI to pull out top topics, challenges, and notable discussions. In parallel, it prepares a cross‑community view so you can see shared trends across all the subreddits you track. After processing everything, it formats the summary to look great in Slack and optionally schedules a weekly run so you don’t have to think about it, delivering a polished update that keeps your team informed without the time sink.

### Key Features

**Weekly Reddit roundup to Slack**: Get a neatly formatted summary of key topics and discussions posted directly to a Slack channel you choose.

**AI topic analysis**: Extracts top themes, challenges, and trends from recent Reddit posts, plus examples and post counts.

**Cross‑community trends**: Synthesizes insights across multiple subreddits to highlight what’s gaining traction broadly.

**Custom focus areas**: Add your own priorities (like “new tools” or “AI automation”) to guide the analysis.

**Smart Slack formatting**: Automatically converts the write‑up into Slack‑friendly bullets, bold headers, and emojis for easy scanning.

**Automatic scheduling**: Set it once to post every Monday morning so your team always starts the week informed.

**Duplicate prevention and storage**: Saves weekly summaries in Redis for 30 days and avoids reposting the same content.

**Error‑tolerant analysis**: Falls back to a simpler summary if structured AI parsing fails, so you still get useful output.

### Instructions

{% stepper %}
{% step %}
Open the automation in CodeWords and connect your Slack workspace, making sure the bot is in the channel you’ll use.
{% endstep %}

{% step %}
Choose the subreddits you want to track and update the search query if you want to narrow or broaden results.
{% endstep %}

{% step %}
Optionally add custom focus areas (like “AI agents, integrations, new tools”) to guide the analysis.
{% endstep %}

{% step %}
Decide how many posts per subreddit to analyze (default 10) and whether to schedule weekly summaries.
{% endstep %}

{% step %}
Hit Run. The automation collects posts, analyzes topics with AI, generates an overall trend view, and posts a Slack‑ready summary.
{% endstep %}

{% step %}
Review the Slack message, tweak subreddits or focus if needed, and turn on weekly scheduling to keep the updates coming every Monday.
{% endstep %}
{% endstepper %}

### Use Cases

This automation is perfect for product, marketing, ops, and community teams who want a quick, reliable pulse on what Reddit is saying about automation and no‑code tools—without living on Reddit. It’s great for weekly team standups, competitive scans, roadmap planning, or inspiration for content. If you track a few niche communities and want a fast way to see what’s trending, this keeps you informed in Slack, where your team already works.

### Frequently Asked Questions

**Q: What exactly does this automation post to Slack?**

**A:** It shares a weekly summary with a title, the week’s date range, top topics, and notable discussions for each subreddit, and a short list of key cross‑community trends—formatted for easy scanning.

**Q: Can I choose which subreddits to monitor?**

**A:** Yes. Provide a list like \["nocode", "automation"] and a simple search query to focus on posts that matter to you.

**Q: Do I need my own Reddit API keys?**

**A:** No. This uses the CodeWords Reddit service to fetch posts—no separate Reddit credentials required.

**Q: How does the AI analysis work?**

**A:** The automation converts recent posts to a clean text format and uses AI technology (gemini-2.5-flash via the CodeWords runtime) to identify topics, themes, and discussions. If structured output fails, it falls back to a simpler summary.

**Q: Why are there two AI models mentioned?**

**A:** gemini-2.5-flash handles topic and trend analysis. gpt-4o is used only to format the final message so it looks great in Slack.

**Q: When does the scheduled post run?**

**A:** By default, it sets a weekly schedule for Monday at 09:00 (cron(0 9 ? \* MON \*)). Timezone follows your runtime environment.

**Q: What if a subreddit has no relevant posts?**

**A:** The automation skips empty results and continues with others. If none return data, you’ll get a clear error so you can adjust subreddits or the query.

**Q: Can I control how many posts it analyzes?**

**A:** Yes. Set posts\_per\_subreddit between 5 and 25 (default is 10).

**Q: What permissions does the Slack bot need?**

**A:** It needs to list channels and post messages. Make sure the bot is added to the target channel and has posting permissions.

**Q: Where is data stored and for how long?**

**A:** A compact record of each week’s summary is stored in Redis for about 30 days to prevent duplicates and help with traceability.

