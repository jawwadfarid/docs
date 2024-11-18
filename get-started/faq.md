# FAQ



<details>

<summary>What can I build?</summary>

CodeWords functions, which as of today are stateless back-end services composed of APIs, code, and tools such as large language models (LLMs) or multimodal models. Stateless means these functions do not retain user data ensuring each function call is independent.

Examples of what you can build include image generation pipelines, document converter workflows, and LinkedIn jobs scraper tools.

</details>

<details>

<summary>What can I currently not build?</summary>

Currently, CodeWords does not support building and generating front-end interfaces directly. While you can develop complex back-end services, we currently only generate simple front-ends. We make it simple to integrate with front-end third-party solutions thanks to the API feature.

</details>

<details>

<summary>Can I use my created CodeWords function as an API?</summary>

Yes. Once you create a function on CodeWords, you can call it as an API using our CodeWords client (a Python library), or the specific endpoint generated for that function. This allows the functions to be integrated into larger systems or to be used standalone for specific tasks.

</details>

<details>

<summary>Can I use existing functions to build new ones?</summary>

Yes, CodeWords allows you to create new functions by composing or utilizing previously created functions. This feature enables the development of increasingly complex services by chaining multiple functions together.

</details>

<details>

<summary>How does CodeWords handle file support?</summary>

CodeWords supports a variety of file formats including text, audio (MP3), video (MP4), images (GIF, PNG), HTML, and various data structures (XML, YAML, JSON). Additionally, document files like PPTX, PDF, and others are supported, making it versatile for different inputs and outputs.&#x20;



</details>

<details>

<summary>What are Integrations in CodeWords?</summary>

Integrations are a set of functions that comprises of:

1. your previously created functions,
2. our curated library of basic functions (Controlnet: Image Editing, Whisper: Convert speech in audio to text, Image Semantic Segmentation, Image Inpainting, Image Generation, General Text Embeddings (GTE), CLIP Text or Images Embeddings, Remove Images Background (Rembg), and QR Code Generator), and
3. [Replicate](https://replicate.com/) APIs.

You may use any combination of the above integrations to enhance your function creation, allowing your function to leverage already-made solutions.

</details>

<details>

<summary>What is the difference between CodeWords Functions and Custom GPTs?</summary>

CodeWords functions and Custom GPTs are two different pieces of software. One is a single-purpose tool whereas the other is a chatbot. Both can deliver the same utility but differ in their mode of interactions.&#x20;

Chatbots like Custom GPTs are like assistants (or agents) with text as the means of communications, whereas tools like CodeWords functions are more akin to a traditional app.

In terms of utility, a CodeWords function can do all that a Custom GPT can do and we plan to support more agent abilities in the future.

</details>

<details>

<summary>What are the benefits of using CodeWords over ChatGPT and other similar platforms?</summary>

Fundamentally, the output from CodeWords is a piece of software (CodeWords function) that is deployed and usable. To get a task done, users would create a CodeWords function and run it. Platforms like ChatGPT are chat assistants users can prompt to achieve a similar action.

While there are overlaps in what CodeWords and ChatGPT can do, CodeWords is primarily aimed at enabling users to create software tools from natural language, hence abstracting the work of a team of developers. ChatGPT is a general-purpose assistant to answer questions and do basic tasks. While it can output code, the user still needs to go through the process of architecting, testing and deploying the code.

</details>

<details>

<summary>What is the difference between CodeWords' chat function and an agent?</summary>

The CodeWords Chat Function, also known as Wordshop, can be thought of as an AI “agent”. It is programmed to help you build the perfect spec to feed into the AI builder.

</details>

<details>

<summary>Where do the CodeWords 'live'?</summary>

CodeWords functions are automatically deployed on the most secure infrastructure, powered by Amazon Web Services, and managed by CodeWords. We offer custom deployment for enterprise customers as well.

</details>

