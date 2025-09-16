# Stock Ticker Sentiment Analyzer

<a href="https://codewords.agemo.ai/run/stock_ticker_sentiment_analyzer" class="button primary">Use this template</a>

## Overview

This automation analyzes stock sentiment for any ticker by aggregating recent conversations from Reddit and Twitter/X, then produces a concise, investor-ready report. It automatically finds the most relevant investing subreddits, scrapes public X search results through Nitter using Firecrawl, and synthesizes themes, bullish and bearish angles, and notable posts into a clear markdown summary. The outcome helps investors, analysts, and product teams quickly understand market chatter, surface catalysts and risks, and track sentiment shifts without manually combing through forums and social feeds.

### Description

This automation delivers a comprehensive social-sentiment brief for a given stock by combining Reddit discussions (via a Reddit connector) and Twitter/X mentions (scraped through Nitter using Firecrawl) into a structured markdown report. It first uses Gemini 2.5 Flash (accessed via the OpenAI client against the CodeWords Gemini runtime) to identify the most relevant investing subreddits for the ticker, then queries those communities through the CodeWords Reddit connector to pull top posts and select comments within a chosen time window.

In parallel, it scrapes X search results from Nitter using Firecrawl to capture recent public mentions without needing platform credentials. After collecting and deduplicating content, it compiles the text and prompts Gemini 2.5 Flash again to produce an organized, markdown-formatted analysis that summarizes overall sentiment, key themes, bullish and bearish arguments, catalysts, risks, and notable links—giving business users a clear, decision-support view of what the market is discussing right now.

### Key Features

**Automatic subreddit discovery**: Uses Gemini 2.5 Flash to suggest the most relevant investing subreddits for each ticker.

**Multi-source aggregation**: Combines Reddit posts and comments with Twitter/X mentions (scraped via Nitter using Firecrawl) for broader coverage.

**Configurable time window**: Filter Reddit discussions by hour, day, week, month, year, or all to focus on the desired recency.

**Deduplication and quality signals**: Remove duplicate links and include Reddit scores to preserve context and engagement indicators.

**AI-written sentiment report**: Generates a structured markdown brief covering overall sentiment, themes, catalysts, risks, and notable sources.

**Notable posts with links**: Surfaces 3–5 most insightful items with direct URLs for quick follow-up reading.

**Parallel fetching for speed**: Gathers Reddit and Twitter/X content concurrently to reduce turnaround time.

### Instructions

{% stepper %}
{% step %}
Choose the ticker you want to analyze (e.g., NVDA) and select a time filter for Reddit (hour, day, week, month, year, or all).
{% endstep %}

{% step %}
Run the automation by sending a POST request or using the built-in runner; no Reddit or X credentials are required.
{% endstep %}

{% step %}
Review the returned report, focusing on Overall Sentiment, Key Themes, Catalysts, Risks, and Notable Posts.
{% endstep %}

{% step %}
Follow the included links to read original discussions for context, and re-run with a different time\_filter to compare sentiment over time.
{% endstep %}
{% endstepper %}

### Use Case

This automation is ideal for equity analysts, investor relations teams, founders, product managers, and traders who need a quick, trustworthy snapshot of market chatter around a ticker—spotting emerging themes, gauging retail sentiment, surfacing catalysts and risks, and tracking how conversations shift after earnings, news, or product launches.

### Frequently Asked Questions

<details>

<summary>What sources does this automation monitor?</summary>

It aggregates Reddit posts and select comments from relevant subreddits via the Reddit connector and scrapes public Twitter/X search results through Nitter using Firecrawl.

</details>

<details>

<summary>Do I need Reddit or X API keys?</summary>

No. This automation uses a Reddit connector and scrapes X via Nitter with Firecrawl, so you don't need platform API keys.

</details>

<details>

<summary>How fresh is the data?</summary>

Reddit content follows the chosen time\_filter, while X mentions are pulled at run time via Nitter scraping, giving near-real-time snapshots.

</details>

<details>

<summary>Can I control which subreddits are used?</summary>

The automation auto-selects investing subreddits via Gemini 2.5 Flash and supplements with common finance subs; to hard-code or exclude specific subs, adjust the configuration in your workspace.

</details>

<details>

<summary>How accurate is the sentiment analysis?</summary>

It uses Gemini 2.5 Flash to summarize patterns in the collected text; accuracy depends on the underlying posts and is best used as directional insight, not financial advice.

</details>

<details>

<summary>Will it include duplicate posts?</summary>

The automation deduplicates by URL to limit repetition and retain a clean set of unique sources.

</details>

<details>

<summary>How long does a run take?</summary>

Typically under a minute, depending on subreddit volume and Firecrawl scraping speed.

</details>

<details>

<summary>Does this automation respect privacy and compliance?</summary>

It only analyzes publicly available content and returns links to public sources; ensure your usage aligns with your organization's compliance policies.

</details>
