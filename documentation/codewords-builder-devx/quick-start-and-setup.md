# Quick Start & Setup

## **Build on Cody the CodeWords Build Agent**&#x20;

[https://chatbot.agemo.ai/](https://chatbot.agemo.ai/)&#x20;



**Build on your own Client**\
\
Before you begin, please ensure you meet the following requirements:
--------------------------------------------------------------------

#### Prerequisites

* Python: Basic knowledge of Python 3.11 or later.
* FastAPI: Familiarity with FastAPI is helpful but not strictly required.
* Browser: A Chromium-based browser (e.g., Google Chrome, Microsoft Edge, Brave) is necessary for utilising browser automation features.

#### Step 1: Obtain Your CodeWords API Key

To get started with building workflows, you'll need an API key from the CodeWords Platform.

1. Sign Up: If you haven't already, sign up for an account on the [CodeWords Platform](https://codewords.agemo.ai/).
2. Navigate to API Keys:
   * Log in to your account.
   * From your dashboard, click on the profile icon located in the bottom-left corner.
   * Select Account.
   * Click on Advanced.
   * Choose API Keys & Environment Variables.
3. Generate and Copy Your Key:
   * Click on Regenerate Key.
   * Refresh the page.
   * Locate and copy your Standard API Key.
4. Store Securely: Store this API key in a secure location. You will need it to authenticate and build your workflows.

### <sup>Step 2: Set Up the CodeWords MCP in a chosen Client</sup>

This step guides you through configuring the CodeWords MCP within a Client

#### On Cursor

1. Access Cursor Settings:
   * Open Cursor.
   * Navigate to Cursor Settings (usually found in the application's preferences or settings menu) (`Cmd/Ctrl + Shift + P`).
   * Go to Tools & Integrations/MCP Tools.
   * Select MCP Tools.
   * Click on New MCP Server.
   * Add a Custom MCP Server.
2.  Configure `mcp.json`:

    * A `mcp.json` file will open. Add the following configuration to this file:

    JSON

    ```json
    {
      "mcpServers": {
        "CodeWords": {
          "url": "https://runtime.codewords.ai/run/devx_mcp/mcp/",
          "headers": {
            "Authorization": "Bearer <YOUR_CODEWORDS_API_KEY>"
          }
        }
      }
    }
    ```

    * Important: Replace `<YOUR_CODEWORDS_API_KEY>` with the actual API key you obtained in Step 1: Obtain Your CodeWords API Key.
    * Save the `mcp.json` file.
3. Connect and Authenticate:
   * Return to Cursor Settings.
   * Locate and connect to CodeWords (Click Log in/Authenticate). This action will initiate an authentication workflow in your browser. Follow the prompts to complete the authentication process.
4. Activate the MCP:
   * Once successfully authenticated, click on the toggle switch next to the CodeWords MCP entry to turn it off/on.
   * Now you should be connected
5.  Select LLM in Cursor Chat:

    * Select Claude-4 Sonnet MAX Mode (you may have to switch off Auto)
    * Go to `Cursor Settings -> Chat -> Turn "Auto-Run Mode" ON`.&#x20;



**On Claude**

1. Go to [https://claude.ai/settings/profile](https://claude.ai/settings/profile).&#x20;
2. Click on Integrations.&#x20;
3. Click on Add integration.&#x20;
   1. Type: `CodeWords` in the Integration name and`https://runtime.codewords.ai/run/devx_mcp/mcp/` as the Integration URL
   2. Click Add and follow the authentication workflow in your browser. Follow the prompts to complete the authentication process.
4.  Once connected, you can view the tools in a new chat.

    1. Make sure to use Claude Sonnet 4 with extended thinking



