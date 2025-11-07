---
description: >-
  Understand how your CodeWords workflows operate with Graph and Code Views —
  visualize data flow or inspect the underlying logic for transparency and
  control.
icon: diagram-project
---

# Workflow Graph and Code View

### Overview

Every automation you build in CodeWords has two perspectives:

* **The Graph View** – a visual map of how your workflow operates.
* **The Code View** – a detailed look at the technical configuration behind it.

Together, they give you complete visibility into what your workflow does and how it works — whether you’re a non-technical creator or an experienced developer.

### 1. The Workflow Graph

#### What Is the Workflow Graph?

The **Workflow Graph** visually represents how your automation runs, similar to a flowchart.\
It shows:

* Where your workflow begins (manually, on a schedule, or through triggers)
* The sequence of steps it performs
* The external tools and services involved
* How data moves from one step to another

Each element is called a **node** and represents a step, and arrows show how data flows between them.

#### Why the Graph View Matters

**For Non-Technical Users**

* **See the big picture:** Understand your workflow at a glance without reading code
* **Track progress:** Watch the workflow being built step-by-step
* **Communicate clearly:** Share the automation’s structure with teammates
* **Spot issues early:** Detect missteps before final deployment

#### What You’ll See

1. **Starting Points**
   * Run Manually — You start it when ready
   * Run on Schedule — Executes automatically (e.g., every day at 9 AM)
   * Run on Trigger — Fires when an event occurs (e.g., new email, form submission)
2. **Steps and Actions**
   * Data processing, API calls, or AI-based analysis
   * Integrations such as Gmail, Slack, LinkedIn, or Google Sheets
3. **Decision Points**
   * Conditional branches, e.g.\
     If order > $1000 → notify finance team
4. **Integrations**
   * Visual icons indicate tools in use (Slack, Gmail, Notion, Stripe, etc.)

#### Accessing the Graph View

When Cody (your CodeWords assistant) builds a workflow, the graph updates automatically during each phase:

* **Planning:** Cody drafts the initial workflow outline
* **Building:** Completed and active steps update live
* **After Deployment:** The final graph serves as your permanent visual reference

**To open it:** Select Graph View in the workflow editor.

<figure><img src="../.gitbook/assets/graph.gif" alt=""><figcaption></figcaption></figure>

### 2. The Code View

#### What Is the Code View?

The **Code View** displays the Python code that defines your workflow’s behavior.\
It’s a text-based configuration showing every step, parameter, and integration — perfect for users who want technical insight or advanced control.

#### Why It’s Useful

* **Transparency:** See the exact logic behind each step
* **Debugging:** Identify issues by reviewing the underlying script
* **Customization:** Fine-tune details not visible in the UI
* **Documentation:** Keep an accurate version of your automation logic

**To open it:** Click Code View in the workflow editor.

#### Viewing the Code

You can access the code in two ways:

**1. During Development**\
Ask Cody:

* “Show me the code for the LinkedIn search step.”
* “Can I review the workflow code before deployment?”\
  Cody displays annotated code with line numbers, explanations, and highlights.

**2. After Deployment**\
Ask Cody to view or compare versions of a deployed workflow.

#### Code Structure Overview

Typical sections include:

* **Header:** Required integrations or dependencies
* **Inputs:** Variables or data sources used
* **Main Logic:** Step-by-step workflow logic
* **Outputs:** Results or returned data
* **Comments:** Human-readable explanations

<figure><img src="../.gitbook/assets/code.gif" alt=""><figcaption><p>Viewing the Code of a Workflow</p></figcaption></figure>

### Putting It All Together

| View Type      | Purpose                                    | Best For                        |
| -------------- | ------------------------------------------ | ------------------------------- |
| **Graph View** | Visualize what happens and in what order   | Non-technical users, reviewers  |
| **Code View**  | Understand _how_ each step works in detail | Developers, technical debugging |

You can build, run, and monitor automations entirely through the visual graph — or dive into code for deeper insight.

### FAQs

<details>

<summary>Do I need to understand code to use CodeWords?</summary>

No. The Graph View exists so anyone can build and understand workflows visually.

</details>

<details>

<summary>When should I use Graph View?</summary>

\
During planning, reviewing builds, or troubleshooting unexpected results.

</details>

<details>

<summary>When should I use Code View?</summary>

When debugging, exporting, or learning how your automation works internally.

</details>

<details>

<summary>Can I modify the code?</summary>

Not directly. But you can also simply describe the change in plain English. Cody will update both the graph and code automatically.

</details>
