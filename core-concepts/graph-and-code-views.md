---
description: >-
  Understand how your CodeWords workflows operate with Graph and Code Views —
  visualize data flow or inspect the underlying logic for transparency and
  control.
icon: diagram-project
---

# Graph and code views

### Overview

Every automation you build in CodeWords has two perspectives:

* **Graph view:** a visual map of how your workflow operates.
* **Code view:** a detailed look at the code and technical configuration behind your workflow. CodeWords writes this for you, and no coding knowledge is needed.&#x20;

Together, they give you complete visibility into what your workflow does and how it works — whether you’re a non-technical creator or an experienced developer.

### Workflow graphs

#### What is a workflow graph?&#x20;

The **workflow graph** visually represents how your automation runs and works in a similar way to a flowchart.

It shows:

* How your workflow begins (manually, on a schedule, or through triggers).
* The sequence of steps it performs.
* The external tools, services, and integrations involved.
* How data moves from one step to another.

Each element is called a **node** and represents a step of your workflow. Nodes are connected by a connection thread that shows how data flows between steps.&#x20;

Usually, automation tools require you to manually connect nodes by dragging, dropping, and configuring their connections. CodeWords doesn't require this: the nodes are mapped out and configured for you.

#### Why the graph view matters

**For non-technical users**

* **See the big picture:** Understand your workflow at a glance without reading any code.
* **Track progress:** Watch the workflow being built and tested step-by-step.
* **Communicate clearly:** Share the automation’s structure with teammates.
* **Spot issues early:** Cody tests each stage of your workflow and you can see that, if there are errors, Cody will work on fixing and retesting them.&#x20;

#### What you’ll see in your graph

1. **Starting points**
   * Run manually: You start it when you're ready
   * Run on a schedule: Executes automatically (e.g., every day at 9 AM)
   * Run on a trigger: Fires when a specific event occurs (e.g., new email, form submission)
2. **Steps and actions**
   * Data processing, API calls, or AI-based analysis
   * Integrations such as Gmail, Slack, LinkedIn, or Google Sheets
3. **Decision points**
   * Conditional branches, e.g.,\
     If order = $1000< → notify finance team
4. **Integrations**
   * Visual icons indicate tools in use (Slack, Gmail, Notion, Stripe, etc.)
   * You can click an integration node to check whether it's connected yet
     * If it has an exclamation mark over it, click the node and select `Connect` to sort the integration connection

#### Accessing the graph view

When Cody (your AI automation assistant) builds a workflow, the graph updates automatically during each phase:

* **Planning:** Cody drafts the initial workflow outline as a visual graph&#x20;
* **Building:** Any completed or active steps are updated live in the todo list
* **After Deployment:** The final graph serves as your visual reference

**To open it:** Select graph view in the workflow editor. The graph view is the default mode.&#x20;

<figure><img src="../.gitbook/assets/graph.gif" alt=""><figcaption></figcaption></figure>

### Code views

#### What is the code view?

The **code view** displays the Python code that defines and underpins your workflow’s behavior. It’s a text-based configuration showing every step, parameter, and integration. It's perfect for users who want technical insight or advanced control.

The code view is there if you want it, but it's not a requirement to use it.&#x20;

#### Why it’s useful

* **Transparency:** See the exact logic behind each workflow step
* **Debugging:** Identify issues by reviewing the underlying script
* **Customization:** Fine-tune details not visible in the UI
* **Documentation:** Keep an accurate version of your automation logic

**To open it:** Click Code View in the workflow editor.

#### Viewing the code

You can easily access the code by selecting the code panel at the top of the chat interface.&#x20;

It will only be visible once Cody has built your graph and written the associated code.&#x20;

You can export the code and use it externally.&#x20;

#### Code structure overview

Typical sections include:

* **Header:** Required integrations or dependencies
* **Inputs:** Variables or data sources used
* **Main Logic:** Step-by-step workflow logic
* **Outputs:** Results or returned data
* **Comments:** Human-readable explanations

<figure><img src="../.gitbook/assets/code.gif" alt=""><figcaption><p>Viewing the Code of a Workflow</p></figcaption></figure>

### Putting it all together

| View Type      | Purpose                                    | Best For                        |
| -------------- | ------------------------------------------ | ------------------------------- |
| **Graph View** | Visualize what happens and in what order   | Non-technical users, reviewers  |
| **Code View**  | Understand _how_ each step works in detail | Developers, technical debugging |

You can build, run, and monitor automations entirely through the visual graph, or you can dive into the code for deeper insight.

### FAQs

<details>

<summary>Do I need to understand code to use CodeWords?</summary>

No. The graph view exists so anyone can build and understand workflows visually.

</details>

<details>

<summary>When should I use the graph view?</summary>

The graph view is your default view when Cody is building your workflow.&#x20;

You can use it for planning, reviewing builds, or troubleshooting unexpected results.

</details>

<details>

<summary>When should I use the code view?</summary>

Once the graph has been built, you'll be able to see the underlying code.&#x20;

This is great if you're more technical and are debugging, want to export the code, or if you're learning how your automation works internally.

</details>

<details>

<summary>Can I modify the code?</summary>

Not directly. Instead, you can describe the change in plain English. Cody will update both the graph and code automatically.

</details>
