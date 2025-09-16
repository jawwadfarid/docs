# Person Finder from Whatsapp

<a href="https://codewords.agemo.ai/run/person_finder_from_whatsapp" class="button primary">Use this template</a>

## Description

This automation listens to your WhatsApp messages and sends back a neat profile summary by combining WhatsApp events, AI technology, and a people-finder search into a single WhatsApp reply. It first registers your phone number and sets a webhook so incoming messages can be analyzed, then uses AI to read what you typed and extract the person’s name, any helpful context (like company and title), and a profile link if you included one. In parallel, it prepares a WhatsApp-friendly format so the results are short, skimmable, and use plain links. After the search runs and results are assembled, it sends a clear confirmation and then a formatted summary back to your chat to produce a quick people snapshot that saves time, reduces manual searching, and keeps your conversation moving.

## Key Features <a href="#key-features" id="key-features"></a>

**One-step setup**: Register your WhatsApp number and start mentioning people right away—no separate app to manage.

**Natural-language capture**: AI analyzes your message to pull out a full name, role, company, and any LinkedIn URL you included.

**Smart search kickoff**: Triggers a people-finder search to gather public social profiles and key details automatically.

**WhatsApp-friendly formatting**: Converts long-form results into short, mobile-ready messages with bold/italics and plain URLs.

**Custom output style**: Add your own formatting rules (e.g., “Only show name, title, and company”) to tailor the reply.

**Extra insights on demand**: Specify additional areas of interest, like certifications or publications, to enrich the result.

**Fast acknowledgments**: Sends a quick “Looking up…” confirmation so you know the search is in progress.

**Secure, API-based flow**: Uses the CodeWords runtime with OpenAI APIs and a WhatsApp trigger to handle messages safely.

## Instructions <a href="#instructions" id="instructions"></a>



{% stepper %}
{% step %}
Open the automation and connect your CodeWords workspace to the WhatsApp trigger and the Person Finder node.
{% endstep %}

{% step %}
Register your WhatsApp number by sending a POST to the registration endpoint (or using the UI form if available) with your phone number and any optional formatting preferences.
{% endstep %}

{% step %}
###

Send a WhatsApp message mentioning a person by name—add helpful context like company or role to improve accuracy.
{% endstep %}

{% step %}
Watch for the quick confirmation message that your lookup started, then give it a few minutes to complete.
{% endstep %}

{% step %}
Review the WhatsApp summary that arrives with links and key details; reply with new names anytime to keep going.
{% endstep %}
{% endstepper %}

## Use Cases <a href="#use-cases" id="use-cases"></a>

This automation is perfect for recruiters, sales teams, founders, and busy operators who need quick context on people mentioned in chats. It helps you validate a person’s details, grab their LinkedIn link, and keep the conversation flowing without switching apps or digging through search results. Great for daily standups, candidate screens, partner intros, or any chat where names come up and you want instant, reliable background info.

## Frequently Asked Questions <a href="#frequently-asked-questions" id="frequently-asked-questions"></a>

<details>

<summary><strong>How do I start using this automation?</strong></summary>

Register your WhatsApp number once, then just mention a person in any message. The automation will analyze the text, run a search, and reply with a formatted summary.

</details>

<details>

<summary><strong>What if I don’t include a full name?</strong></summary>

The AI does its best with what you send, but including a full name and quick context, like company or role, improves accuracy. If it can’t find enough to search, it will ask you for more details.

</details>

<details>

<summary><strong>How long do results take?</strong></summary>

You’ll get a confirmation right away, and results typically arrive in about 4–5 minutes, depending on the search depth and sources.

</details>

<details>

<summary><strong>Can I customize the reply format?</strong></summary>

Yes. During registration, add a message like “Only show name, title, and company.” The automation will follow your formatting preference for future replies.

</details>

<details>

<summary><strong>What information can it include?</strong></summary>

By default, it looks for a full name, role, company, and public profile links (like LinkedIn). You can also request extras such as certifications or recent publications.

</details>

<details>

<summary><strong>Does this work in group chats?</strong></summary>

Yes. If the registered number receives the message event and the text mentions a person with some context, the automation will try to process it and reply.

</details>

<details>

<summary><strong>Which tools does it use under the hood?</strong></summary>

It runs on FastAPI and uses OpenAI (via the CodeWords runtime) for AI extraction and formatting, a WhatsApp trigger for inbound/outbound messages, and a Person Finder step to gather public profiles.

</details>

<details>

<summary><strong>Is my data secure?</strong></summary>

Messages are processed through the CodeWords runtime with your API key. Only the necessary text is analyzed to extract names and context, and results are sent back to your WhatsApp number.

</details>

<details>

<summary><strong>What happens if the automation can’t find a person?</strong></summary>

You’ll get a friendly prompt asking for a clearer name or more context so it can try again.

</details>

<details>

<summary><strong>Can I stop or pause it?</strong></summary>

You can unregister your number from the WhatsApp trigger in your CodeWords workspace, or disable the automation temporarily if you don’t want new messages processed.

</details>
