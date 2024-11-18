# Prompt Writing

**1. What makes a good prompt for a CodeWords function?**

A good prompt should describe the expected inputs and outputs. It should detail the processing steps involved.

{% hint style="info" %}
:bulb: The more detailed your prompt, the higher chance the function will align with your expectations.

A vague description would leave a lot of decision to the Builder, it will still be able to build something but it might not be what you expect, whereas a detailed one would ensure that it builds what you have in mind.

Pro Tip: get inspiration from the templates
{% endhint %}

***

**2. How detailed should the steps in a prompt be?**

The steps should be specific enough to convey the required actions without ambiguity. Each step should be actionable and independent, referencing the available integrations. See what you can use to build in the [Integrations and Packages](https://www.notion.so/CodeWords-Documentation-136c873bb9c7406d8ebf5ac8c4b5dcba?pvs=21) section. Check out the [Example Library](https://www.notion.so/CodeWords-Documentation-136c873bb9c7406d8ebf5ac8c4b5dcba?pvs=21) for inspiration on how the prompt should look like.



<table data-full-width="true"><thead><tr><th width="447">Prompt</th><th>Prompt Quality<select><option value="rrEOaAt6nLlh" label="Vague" color="blue"></option><option value="pz2UuCOfZ2Pr" label="Concise" color="blue"></option><option value="mDO03pxMJ0BR" label="Detailed" color="blue"></option></select></th><th>Success Rate<select><option value="I5GyDE1r3X5k" label="Medium" color="blue"></option><option value="ANd2SMYEZXVH" label="High" color="blue"></option></select></th><th>Accuracy Rate<select><option value="jaump1z31hkk" label="Low" color="blue"></option><option value="s1KX4hoL9KGe" label="Medium" color="blue"></option><option value="bacTznFiLhPJ" label="High" color="blue"></option></select></th></tr></thead><tbody><tr><td>I want an app that takes multiple articles on the same topic and summarise them into one, easy to read article with as minimal bias as possible<br></td><td><span data-option="rrEOaAt6nLlh">Vague</span></td><td><span data-option="I5GyDE1r3X5k">Medium</span></td><td><span data-option="jaump1z31hkk">Low</span></td></tr><tr><td>I want an app that takes multiple articles on the same topic and summarise them into one, easy to read article with as minimal bias as possible. The input is a list of URLs to the articles. Summarise and extract the name of the publisher of the article. Finally, concatenate all of the summaries together with the publisher's name and merge all the summaries together.<br></td><td><span data-option="pz2UuCOfZ2Pr">Concise</span></td><td><span data-option="ANd2SMYEZXVH">High</span></td><td><span data-option="s1KX4hoL9KGe">Medium</span></td></tr><tr><td><p>I want an app that takes multiple articles on the same topic and summarises them all into one succinct, easy to read article with as minimal bias as possible. Here are the steps it should follow:</p><ol><li>Take a list of URLs to the articles as input.</li><li>Use the Web Renderer API to pull content for each of the articles.</li><li>Use the GPT-based AI API to summarise and extract the name of the publisher of the article.</li><li>Concatenate all of the summaries together with the publisher's name and use the GPT-based AI to merge all the summaries together.</li></ol><p>The output should be a text paragraph.<br></p></td><td><span data-option="mDO03pxMJ0BR">Detailed</span></td><td><span data-option="ANd2SMYEZXVH">High</span></td><td><span data-option="bacTznFiLhPJ">High</span></td></tr></tbody></table>

{% hint style="info" %}
:bulb:Pro Tip: use the Check & Enhance feature to let our AI rewrite your prompt
{% endhint %}

***

**3. What are common pitfalls to avoid in problem statements?**

Avoid vagueness in describing what the tool should do, omitting the types of inputs or outputs, and assuming the system will manage state or user sessions. Also, avoid overly complex descriptions that go beyond the capabilities of stateless processing or the integrations available.

***

**4. Can you provide an example of how to format inputs and outputs in a problem statement?**

Yes, always specify what form the inputs will take (e.g., a URL, a file object like image.png, a JSON object) and describe the expected format of the outputs (e.g., a text file, JSON response). This clarity helps in setting the correct expectations and the technical scope of the function.

{% hint style="info" %}
{% code overflow="wrap" fullWidth="true" %}
```markup
Inputs:
- `video.mp4`: The video file to be processed.

Outputs:
- `translated_text.txt`: A text file containing the transcript translated into German.
```
{% endcode %}
{% endhint %}

***

**5. What should I include if the problem involves external data sources?**

If your function needs to interact with external data sources like web pages or databases, specify any necessary authentication details or API keys as inputs.

{% hint style="info" %}
:bulb: Or get in touch with us at [support@agemo.ai](mailto:support@agemo.ai)
{% endhint %}
