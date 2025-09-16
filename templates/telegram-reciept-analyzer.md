# Telegram Reciept Analyzer

<a href="https://codewords.agemo.ai/run/telegram_receipt_analyzer" class="button primary">Use this template</a>

## Overview

This automation turns receipt photos into clean, structured summaries you can read at a glance or send back to customers in Telegram. Snap a picture of a receipt, share it with your Telegram bot, and the automation uses AI to extract the merchant, date, items, taxes, and totals—then replies with a nicely formatted breakdown. You can also call it directly through an API if you prefer. It’s built with FastAPI, taps into the Telegram Bot API for messages, and uses OpenAI’s vision capabilities to read receipts accurately.

## Description

This automation analyzes receipt photos and returns a clean transaction summary by combining Telegram messages, AI technology, and a simple web API into a formatted response that’s easy to share. It first listens for receipt photos sent to your Telegram bot or accepts an image URL through the root API endpoint, then uses AI to read the image and pull out the merchant, items, taxes, and totals in a structured way. In parallel, it handles both webhook and short-polling flows for Telegram so you can use whichever setup fits your environment. After processing the image and formatting the results, it replies right in Telegram or returns a JSON response, producing a clear transaction summary that saves time on manual data entry and makes expense tracking easier.

## Key Features

**Telegram receipt parsing**: Send a photo to your bot and get an instant, readable summary.

**AI-powered vision**: Uses OpenAI’s vision model to extract merchants, dates, items, taxes, and totals from images.

**Clean, chat-friendly output**: Replies in Telegram with a tidy breakdown of items, amounts, and key details.

**Direct API access**: Post an image URL to the root endpoint and get structured results back as JSON.

**Two Telegram modes**: Works with webhooks or simple short polling—use what’s easiest for you.

**Pipedream integration option**: Send replies via Pipedream’s Telegram Bot API action when needed.

**Error-aware formatting**: Skips missing fields gracefully and focuses on the most useful details.

**Logs for debugging**: Helpful logging around payloads, image handling, and response generation.

## Instructions

{% stepper %}
{% step %}
Open the automation and connect your accounts: add your Telegram bot token and OpenAI API key.
{% endstep %}

{% step %}
Decide how you want to receive messages: set a Telegram webhook to the /webhook endpoint or use the /check-messages endpoint for short polling.
{% endstep %}

{% step %}
Test it with an image URL: POST to the root endpoint (/) with a receipt image URL to confirm AI parsing works.
{% endstep %}

{% step %}
Send a real receipt: In Telegram, send a receipt photo to your bot and wait for the formatted reply.
{% endstep %}

{% step %}
Review the results: Check the item list, subtotal, tax, and total; forward or copy the summary as needed.
{% endstep %}

{% step %}
Tweak and try again: If fields are missing, resend a clearer photo or a different angle for better extraction.
{% endstep %}
{% endstepper %}

## Use Cases

This automation is perfect for anyone who collects receipts and wants quick, accurate summaries without typing—think small business owners, finance teams, bookkeepers, and frequent travelers. It’s also great for support or operations teams that need to confirm totals and taxes from customer uploads, or for expense-tracking workflows where a fast, chat-friendly breakdown makes reviews easier.

## Frequently Asked Questions

<details>

<summary><strong>What happens when I send a receipt photo in Telegram?</strong></summary>

The automation fetches the photo via the Telegram Bot API, runs AI analysis on the image, and replies in chat with a structured breakdown of items, totals, and key details.

</details>

<details>

<summary><strong>Can I use it without Telegram?</strong></summary>

Yes. You can call the root API endpoint (/) with a receipt image URL and get a JSON response with the parsed data and a formatted summary string.

</details>

<details>

<summary><strong>Does it support both webhooks and polling?</strong></summary>

It does. Use /webhook for a webhook setup or /check-messages for short polling if you don’t want to configure webhooks.

</details>

<details>

<summary><strong>What AI model does it use?</strong></summary>

It uses OpenAI’s vision-enabled chat model (configured as gpt-5). You won't need an OpenAI API key, and CodeWords will provide access to the vision-capable model for your account.

</details>

<details>

<summary><strong>What if my receipt is crumpled or low quality?</strong></summary>

AI results improve with clearer images. Try retaking the photo in good lighting, fill the frame with the receipt, and keep it in focus for best results.

</details>

<details>

<summary><strong>Will it extract taxes, PO numbers, and addresses?</strong></summary>

Yes. The schema includes tax amounts and rates, PO number, bill-to/ship-to addresses, payment terms, bank details, and more—fields are filled when visible on the receipt.

</details>

<details>

<summary><strong>How does the Telegram reply get sent?</strong></summary>

By default, it uses the Telegram Bot API (sendMessage). There’s also an option to send replies through a Pipedream Telegram action using the CodeWords client.

</details>

<details>

<summary><strong>What endpoints are available?</strong></summary>

POST / analyzes an image URL, POST /check-messages polls Telegram and replies to new photo messages, and POST /webhook handles inbound Telegram events for webhook setups.

</details>

<details>

<summary><strong>Does it support multiple currencies and languages?</strong></summary>

It can extract prices and currency symbols from what it reads on the image. Multilingual OCR depends on the model’s capabilities; clear receipts in major languages work best.

</details>

