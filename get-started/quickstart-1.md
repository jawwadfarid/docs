# Quickstart

## Building your first automation

#### Automated Web Scraper & Gmail Summarizer

This automation scrapes the content of a given web page, generates a concise summary using AI, and emails it directly to your inbox.

#### 1. Triggers with a URL

_The automation starts when you provide a web page URL. This can be done manually each time you want to summarize a page or set up on a schedule to monitor a specific URL for new content._

#### 2. Scrapes Website Content

_The workflow visits the provided URL and extracts the text-based content from the page. It intelligently pulls the main body of information, ignoring ads, navigation bars, and footers to capture only the relevant data._

#### 3. Generates an AI-Powered Summary

_Using AI, the automation processes the scraped text to create a concise summary. It identifies the key points, main arguments, and important data, condensing the information into a few easy-to-read paragraphs._

#### 4. Sends the Summary via Gmail

_The workflow automatically sends the generated summary to your Gmail address. The email is professionally formatted, with the article's title as the subject line and the summary in the body, allowing you to get the key insights without ever leaving your inbox._

## Step 1: Planning your automation

**Describe your process and tell Cody what you want to automate**

> _"Build me a workflow which scrapes data from a url and sends the summary to my gmail."_

{% embed url="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FC0KQHHlFG9y1F0pBotb8%2Fuploads%2F6uIsjCxz1BNbwZijPqVN%2Fquickstart_small.mp4?alt=media&token=a68bd407-d46e-41bd-9da0-fce859a2cf61" %}

**Cody researches what's possible**

Cody will:

* Check if there are existing templates that match your needs (30+ proven templates available)
* Explore the 2700+ app integrations available through the platform
* Verify all the connections and data sources needed

**Review the automation plan**

Cody presents a plan:

1. **Web scraping**: Extract the main text content from the provided URL.
2. **AI summarization**: Generate a concise, easy-to-read summary of the scraped content.
3. **Email composition**: Draft an email containing the AI-generated summary.
4. **Gmail delivery**: Send the summary email directly to your inbox for review.

Once you approve, Cody starts building.

## Step 2: Incremental building

**Web Content Extraction**

What Cody builds:

* Takes a public URL as input.
* Navigates to the web page.
* Extracts the primary text content, ignoring ads, sidebars, and footers.

Cody tests with a sample Input:

```
Input: https://www.nationalgeographic.com/science/article/ancient-dna-reveals-woolly-mammoths-final-years

Results:
✅ URL Accepted: Valid National Geographic article link.
✅ Page Scraped: Successfully loaded and parsed the page structure.
✅ Content Extracted: 1,200 words of article text captured.
✅ Confidence: 98% relevant content extraction.
```

**AI Summary & Email Delivery**

What Cody adds:

* Processes the extracted text using an advanced AI model.
* Generates a concise, bulleted summary of the key findings.
* Connects securely to your Gmail account.
* Composes and sends the summary to your designated email address.

**Cody** **Testing results:**

```
✅ Created Summary: AI generated a 4-point summary.
✅ Connected to Gmail: Authenticated with your.email@gmail.com.
✅ Email Composed: Subject and body formatted as shown above.
✅ Email Sent: Delivered to your inbox successfully.
```

## Step 3: Final testing

Cody runs the complete workflow end-to-end to ensure everything works together seamlessly.

Cody asks for final confirmation:

{% code overflow="wrap" %}
```
The complete automation worked perfectly with the National Geographic article. The website was scraped, the AI generated a clear summary of the key scientific findings, and the email arrived in your inbox with the correct formatting and a link to the original source. Are you completely satisfied with how this automation works?

1. Yes, it's exactly what I wanted.                
2. I'd like to adjust something first
```
{% endcode %}

## Step 4: Congratulations, Your Automation is Ready

Once you've confirmed that you're happy with the output, Cody will provide you with your automation URL:

```
https://codewords.agemo.ai/run/web-summarizer-automation-xyz789
```

And Cody provides you with a summary of the automation that you have built.

## Step 5: Troubleshooting

**Website Scraping Failures**

* **Check the URL**: Ensure the link is correct and the page is publicly accessible (not behind a paywall or login).
* **Website blocks scraping**: Some complex, JavaScript-heavy sites may resist automated scraping. Try with a different, simpler article-based site to confirm the workflow is active.
* **No text found**: The page might be image- or video-heavy with very little text to analyze.

**AI Summary Issues**

* **Summary quality**: If the summary is poor, try a different article. Highly technical or abstract content can be more challenging for the AI to condense.
* **Adjust prompt**: You can refine the instructions for the AI, such as asking for a "3-bullet summary" or a "one-paragraph summary for a 5th grader."

**Gmail Delivery Problems**

* **Check permissions**: Re-authenticate your Gmail account to ensure the connection is active and has the necessary permissions to send emails.
* **Check spam folder**: If the email doesn't arrive, check your spam or junk folder and mark it as "not spam" to train your inbox.

## Summary

You've built a powerful information-gathering automation that:

* Accepts any public article URL as an input.
* Extracts the core content automatically.
* Generates an AI-powered summary of the key points.
* Delivers the summary directly to your Gmail inbox.

