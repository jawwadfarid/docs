# CodeWords DevX MCP Agent: Your AI Development Toolkit

The CodeWords DevX MCP (Model Context Protocol) Agent is an advanced AI assistant designed to streamline and enhance your workflow development on the CodeWords platform. It provides a comprehensive suite of tools to help you build, deploy, manage, and monitor your CodeWords workflows efficiently.

### Overview of Capabilities

Our agent empowers you to:

* Explore CodeWords Features: Understand the platform's capabilities and determine the best approach for your specific requirements.
* Develop Workflows: Create new workflows from scratch or customise existing templates with ease.
* Deploy and Manage: Seamlessly deploy and manage your workflows directly on the CodeWords platform.
* Integrate with Services: Connect to over 2000 third-party services via Pipedream, expanding your workflow's reach.
* Utilise Built-in Services: Access a library of pre-built services for common tasks, such as interacting with Large Language Models (LLMs) or web scraping.
* Follow Best Practices: Leverage embedded documentation and guidance to ensure your workflows are robust and optimised.

### Understanding the Agent's Tools

The agent's functionalities are organised into distinct categories to help you quickly find the right tool for the job.

#### 1. Information & Exploration Tools

These tools help you understand the CodeWords platform, discover best practices, and explore available resources.

* <mark style="color:purple;">`get_workflow_building_instructions`</mark>
  * Purpose: Get comprehensive guidance on the entire workflow development lifecycle.
  * When to Use: This should be your first point of reference when you have questions about CodeWords development.
  * What it Does: Provides a complete guide from initial exploration to deployment.
  * Parameters: None required.
* <mark style="color:purple;">`list_practices`</mark>
  * Purpose: Discover available best practices and development patterns.
  * When to Use: When you're exploring CodeWords methodologies or seeking guidance on specific topics.
  * What it Does: Lists practice sections categorised by type (e.g., CodeWords, LinkedIn, Monitoring).
  * Parameters:
    * `practice_type`: Filter practices by category (e.g., "codewords", "linkedin", "monitoring", "deep\_research", "library\_services", "all").
    * `include_descriptions`: Set to `true` to include brief descriptions of each practice.
  * Returns: A structured list of practice sections with unique IDs for detailed viewing.
* <mark style="color:purple;">`view_practice`</mark>
  * Purpose: Get detailed content for specific best practice sections.
  * When to Use: After using `list_practices` to identify the specific guidance you need.
  * What it Does: Retrieves the full content of a practice section, including code examples and explanations.
  * Parameters:
    * `section_ids`: A list of specific section IDs to retrieve (e.g., `["3.1", "9.2"]`).
    * `practice_type`: The category of practices to read from (e.g., "codewords").
    * `include_code_examples`: Set to `true` to include code blocks within the content.
    * `include_subsection_content`: Set to `true` to include content from subsections.
  * Returns: Detailed Markdown content containing embedded best practices.
* <mark style="color:purple;">`list_template_workflows`</mark>
  * Purpose: Discover available pre-built workflow templates.
  * When to Use: When you're looking for starting points, inspiration, or ready-to-use solutions.
  * What it Does: Returns a curated list of pre-built workflow templates.
  * Parameters:
    * `category`: Filter templates by category (e.g., "all", "linkedin", "monitoring", "enrichment", "integration").
    * `include_full_description`: Set to `true` to include complete descriptions for each template.
  * Returns: A list of templates with their names, IDs, and descriptions.
* <mark style="color:purple;">`discover_library_services`</mark>
  * Purpose: Explore the built-in services provided by CodeWords.
  * When to Use: To understand what out-of-the-box functionality is available to you.
  * What it Does: Lists and allows execution of built-in services (e.g., LLMs, Firecrawl).
  * Parameters:
    * `operation`: Specify "list" to view available services or "execute" to run a service.
    * `service_id`: The ID of the service to execute (required for "execute" operation).
    * `inputs`: Parameters required for the service execution.
  * Returns: Either a catalog of services or the results of a service execution.
  * Note: It's recommended to study library services practices first, as services like LLMs and Firecrawl require specific client patterns.
* <mark style="color:purple;">`discover_pipedream_integrations`</mark>
  * Purpose: Explore over 2000 third-party integrations available through Pipedream.
  * When to Use: Before implementing any third-party integration in your workflow.
  * What it Does: Allows you to search for integrations, explore their capabilities, check authentication status, and even test actions.
  * Operations (via `operation` parameter):
    * `search`: Find integrations by keyword.
    * `actions`: List available actions for a specific integration.
    * `schema`: Get detailed parameter specifications for an action.
    * `check_auth`: Verify the authentication status for an integration.
    * `execute`: Test actions to understand their output (requires user consent).
  * Critical: You must declare `PIPEDREAM_{APP_SLUG}_ACCESS` in your workflow header for Pipedream integrations to work.

#### 2. Workflow Development Tools

These tools assist you directly in writing, editing, and planning your CodeWords workflows.

* <mark style="color:purple;">`write_workflow_file`</mark>
  * Purpose: Write workflow code to files and obtain shareable URLs.
  * When to Use: During implementation to save the Python code you generate.
  * What it Does: Saves code locally and/or uploads it to CodeWords storage.
  * Special Feature: Use `workflow_code="workflow_skeleton"` to get a basic workflow template.
  * Parameters:
    * `workflow_code`: The Python code for your workflow, or "workflow\_skeleton" to get a template.
    * `filename`: The desired name for your file.
    * `local_path`: (Optional) A local path to save the file.
    * `upload_to_storage`: Set to `true` to upload the file to CodeWords storage and get a shareable URL.
  * Returns: File paths, URLs (if uploaded), and analysis of the code (dependencies, environment variables, etc.).
* <mark style="color:purple;">`edit_workflow`</mark>
  * Purpose: Make targeted edits to existing workflow files.
  * When to Use: For iterative improvements, bug fixes, or minor adjustments to your workflows.
  * What it Does: Replaces specific sections of code within a workflow file.
  * Important: The `old_str` you provide must be unique within the file to ensure the correct section is replaced.
  * Parameters:
    * `file_path`: The path or URL to the workflow file you want to edit.
    * `old_str`: The exact text to be replaced (must be unique).
    * `new_str`: The new code that will replace `old_str`.
    * `description`: A concise description of the change you are making.
  * Supports: Both local files and remote URLs (e.g., S3).
* <mark style="color:purple;">`create_implementation_plan`</mark>
  * Purpose: Create structured implementation plans with embedded best practices.
  * When to Use: After you've created a workflow skeleton, but before you begin the detailed implementation.
  * What it Does: Formats your implementation steps and integrates relevant CodeWords best practices.
  * Parameters:
    * `steps`: A list of implementation steps, including references to relevant practices.
  * Returns: A Markdown implementation plan with embedded guidance.
* <mark style="color:purple;">`validate_workflow`</mark>
  * Purpose: Validate your workflow code without needing to deploy it.
  * When to Use: Frequently, before deployment, to catch potential issues early.
  * What it Does: Performs a comprehensive validation against CodeWords standards.
  * Checks Include: Syntax, PEP 723 headers, FastAPI structure, declared dependencies, and more.
  * Parameters:
    * `workflow_code_or_file_url`: The workflow code directly, a local file path, or a URL to the workflow file.
  * Returns: The validation status and a detailed report of any findings.

#### 3. Deployment & Management Tools

These tools handle the deployment of your workflows to the CodeWords platform and manage their secure configurations.

* <mark style="color:purple;">`deploy_workflow`</mark>
  * Purpose: Deploy your workflows to the CodeWords platform, making them live.
  * When to Use: After your workflow has been validated and is ready for production or testing.
  * What it Does: Manages the deployment process, including dependency extraction and service registration.
  * Parameters:
    * `workflow_code_or_file_url`: The workflow code or a URL to the workflow file.
    * `workflow_name`: A human-readable name for your workflow.
    * `workflow_id`: A unique identifier for your workflow (should end with `_{uuid}`).
    * `description`: A brief description of what the workflow does.
    * `public`: Set to `true` if the workflow should be publicly accessible.
    * `override_existing`: Set to `true` to update an existing workflow with the same `workflow_id`.
    * `is_template`: Set to `true` if this workflow should be marked as a template for others to use.
  * Returns: The deployment result, including details about the deployed service.
* <mark style="color:purple;">`retrieve_workflow`</mark>
  * Purpose: Get the existing code and metadata for a deployed workflow.
  * When to Use: To inspect, modify, or clone an existing workflow.
  * What it Does: Fetches the complete source code of a specified workflow.
  * Parameters:
    * `workflow_id`: The ID of the workflow you want to retrieve.
    * `upload_code`: Set to `true` to upload the code to CodeWords storage and get a shareable URL.
  * Returns: The workflow code, its metadata, and an optional file URL if `upload_code` was true.
* <mark style="color:purple;">`manage_user_secrets`</mark>
  * Purpose: Manage secure environment variables for your workflows.
  * When to Use: When setting up API keys, credentials, or other sensitive information for integrations.
  * What it Does: Securely stores and retrieves secrets that are automatically injected into your workflows at runtime.
  * Operations (via `operation` parameter):
    * `add`: Store a new secret (provide `name` and `value`).
    * `get`: Retrieve the value of a specific secret (provide `name`).
    * `list`: List the names of all stored secrets.
  * Security: Secrets are encrypted and only made available to your workflow during execution.
  * Important: You must declare any secrets you intend to use in your workflow's PEP 723 header for them to be accessible.

#### 4. Execution & Monitoring Tools

These tools allow you to run your workflows, monitor their progress, and retrieve their outputs and logs.

* <mark style="color:purple;">`run_workflow`</mark>
  * Purpose: Execute your deployed workflows with specific inputs.
  * When to Use: For testing workflows, or to programmatically trigger their execution.
  * What it Does: Executes workflows either synchronously (waits for completion) or asynchronously (runs in the background).
  * Parameters:
    * `workflow_id`: The ID of the workflow you want to run.
    * `inputs`: A dictionary of input parameters for the workflow.
    * `run_async`: Set to `true` to run the workflow asynchronously.
    * `timeout_seconds`: The maximum time (in seconds) to wait for synchronous execution.
  * Returns: Results immediately if run synchronously, or a request ID for tracking if run asynchronously.
* <mark style="color:purple;">`get_workflow_logs`</mark>
  * Purpose: Retrieve logs from your workflow executions.
  * When to Use: To monitor the progress of a running workflow or debug issues in completed runs.
  * What it Does: Fetches or streams log entries from specified workflow requests.
  * Parameters:
    * `request_id`: The request ID obtained from an asynchronous execution.
    * `follow`: Set to `true` to stream logs as they are generated.
    * `max_entries`: The maximum number of log entries to return.
  * Returns: A list of log entries, including timestamps and messages.
* <mark style="color:purple;">`get_workflow_output`</mark>
  * Purpose: Get the final output from completed workflow executions.
  * When to Use: To retrieve the results from asynchronous workflow runs.
  * What it Does: Waits for the specified workflow execution to complete and then returns its final output.
  * Parameters:
    * `request_id`: The request ID from an asynchronous execution.
    * `timeout_seconds`: The maximum time (in seconds) to wait for the workflow to complete.
  * Returns: The final workflow output and its execution status.
* <mark style="color:purple;">`get_workflow_requests`</mark>
  * Purpose: Get the recent execution history for a specific workflow.
  * When to Use: For debugging workflows that were tested on the CodeWords UI or to analyze execution patterns.
  * What it Does: Retrieves a list of recent executions, including their status and timing information.
  * Parameters:
    * `workflow_id`: The ID of the workflow you want to check.
    * `limit`: The number of recent requests to retrieve.
  * Returns: A list of recent executions, each with a request ID for detailed analysis.
  * Essential for: Debugging workflows that have been triggered via the UI.

#### 5. File Management Tools

These tools enable you to upload and download files to and from CodeWords storage.

* <mark style="color:purple;">`upload_file`</mark>
  * Purpose: Upload files to CodeWords' secure storage.
  * When to Use: For storing outputs, sharing files, or preparing inputs for your workflows.
  * What it Does: Uploads content to secure storage and provides a shareable URL.
  * Parameters:
    * `file_content_or_local_path`: The content of the file or a local path to the file.
    * `filename`: The desired name for the uploaded file.
    * `content_type`: The MIME type of the file (e.g., "text/plain", "application/json").
    * `is_local`: Set to `true` to get a shell command for local uploading instead of performing the upload directly.
  * Local Mode: When `is_local` is true, it returns shell commands suitable for local development environments.
* <mark style="color:purple;">`download_file`</mark>
  * Purpose: Download files from specified URLs.
  * When to Use: To retrieve files you've uploaded, access shared content, or process external files.
  * What it Does: Downloads the content of a file from a given URL.
  * Parameters:
    * `file_url`: The URL of the file to download.
    * `decode_text`: Set to `true` to decode the downloaded content as UTF-8 text.
    * `is_local`: Set to `true` to get a shell command for local downloading instead of performing the download directly.
    * `local_path`: Where to save the file locally (only applicable if `is_local` is true).
  * Supports: CodeWords storage URLs, public URLs, and pre-signed URLs.

#### 6. Sandbox Creation (HTTP Endpoint)

This special tool allows for the creation of temporary development environments.

* Sandbox Creation Endpoint
  * Purpose: Create live sandboxes running the DevX service.
  * Access: This is accessed via a `POST` request to the service root.
  * When to Use: For setting up temporary, isolated development environments.
  * What it Does: Deploys the DevX service within an isolated sandbox.
  * Parameters:
    * `codewords_api_key`: Your CodeWords API key.
    * `service_type`: "Streamable HTTPS (MCP)" or "Server-Sent Events (SSE)".
    * `duration_minutes`: How long the sandbox should run (between 1 and 60 minutes).
  * Returns: Connection instructions and the service URI for the newly created sandbox.

### How the Agent Works: Typical Development Workflow

The CodeWords DevX MCP Agent is designed to guide you through a systematic development process, ensuring best practices are followed at each stage.

#### Phase 0: Intent Understanding (Discovery & Planning)

1. Understand the Goal: Begin by clearly defining what you want your workflow to achieve.
2. Explore Capabilities:
   * Use `get_workflow_building_instructions` to get an overall understanding.
   * Use `list_practices` to explore available best practices by domain (e.g., "linkedin", "monitoring").
   * Dive deeper into specific practices with `view_practice`.
   * Discover out-of-the-box functionalities using `discover_library_services`.
   * Investigate third-party integration possibilities with `discover_pipedream_integrations`.

#### Phase 1: Requirements Analysis

1. Gather Context: Ensure you have all necessary information through conversation or research.
2. Find Inspiration:
   * Use `list_template_workflows` to find similar existing patterns or starting points.
   * If applicable, use `retrieve_workflow` to examine existing implementations that might serve as a reference.

#### Phase 2: Research & Pattern Analysis

1. Deep Dive into Best Practices: Use `view_practice` to study relevant best practices for your specific implementation.
2. Integration Exploration: Utilize `discover_pipedream_integrations` with the "search," "actions," and "schema" operations to fully understand potential third-party integrations.
3. Component Testing: If uncertain about a component's behavior, use the "execute" operations of `discover_library_services` or `discover_pipedream_integrations` to test and understand their outputs.

#### Phase 3: Implementation Planning

1. Structure Your Plan: Use `create_implementation_plan` to generate a structured plan with embedded best practices.
2. Document Requirements: Outline any specific integration requirements.
3. Manage Credentials: Set up necessary API keys and credentials using `manage_user_secrets`.

#### Phase 4: Implementation (Coding)

1. Start with a Skeleton: Begin by using `write_workflow_file` with `workflow_code="workflow_skeleton"` to create the basic structure.
2. Iterative Development: Follow your implementation plan and use `edit_workflow` sequentially to add your code.
3. Frequent Validation: After making significant changes, use `validate_workflow` to proactively catch any issues.

#### Phase 5: Deployment

1. Go Live: Use `deploy_workflow` to deploy your validated workflow to the CodeWords platform.
2. Initial Testing: Run your workflow with sample data using `run_workflow`.
3. Monitor Execution: Use `get_workflow_logs` to monitor the workflow's progress and identify any immediate issues.

#### Phase 6: Iteration & Refinement

1. Analyze History: Use `get_workflow_requests` to review past executions and identify patterns or errors, especially for UI-tested workflows.
2. Debug and Fix: Based on logs and analysis, use `edit_workflow` to apply fixes, referencing best practices as needed.
3. Repeat Testing: Continue testing until the workflow meets your requirements and user satisfaction.

### Best Practices for Using the Agent's Tools

To maximise your efficiency and build high-quality workflows, consider these critical success factors and common tool combinations:

#### Critical Success Factors

1. Always Study Practices First: Before attempting any implementation, use `view_practice` to understand the recommended approaches.
2. Test Uncertain Components: Use "execute" operations of integration tools to thoroughly understand their outputs before integrating them into your workflow.
3. Follow Sequential Development: Utilise `edit_workflow` step-by-step, building your workflow incrementally.
4. Validate Frequently: Regularly use `validate_workflow` after any major code changes to catch issues early.
5. Monitor Executions: Actively use logging and monitoring tools for debugging and performance analysis.

#### Common Tool Combinations

* Exploration: `list_practices` → `view_practice` → `discover_library_services`
* Integration Research: `discover_pipedream_integrations` (search → actions → schema → check\_auth)
* Development: `write_workflow_file` → `edit_workflow` → `validate_workflow` → `deploy_workflow`
* Testing: `run_workflow` → `get_workflow_logs` → `get_workflow_output`
* Debugging: `get_workflow_requests` → `get_workflow_logs` → `edit_workflow`

#### Security Considerations

* Secrets Management: Always use `manage_user_secrets` for storing and accessing sensitive credentials (e.g., API keys). Never hardcode them directly in your workflow.
* Environment Variables: Ensure all secrets or environment variables your workflow needs are declared in your workflow's PEP 723 header.
* User Consent: When interacting with tools that perform actions with side effects (like Pipedream `execute` operations), always obtain explicit user permission.
* URL Handling: Present any authentication or external URLs exactly as provided by the agent to ensure security and proper functionality.

This documentation provides comprehensive guidance for leveraging each tool within the CodeWords DevX MCP Agent. These tools are designed to work together seamlessly, supporting the complete workflow development lifecycle from initial exploration to production deployment.
