# Building web apps with a CodeWords back-end

## 0. Prerequisites

✅ **Deploy and test your CodeWords service first**

* Your CodeWords workflow must be working properly
* Test it thoroughly with actual inputs
* Get your service ID (e.g., `linkedin-enricher`)&#x20;

✅ **Get your CodeWords API key**

* Visit [CodeWords Dashboard](https://codewords.agemo.ai/account/keys)
* Copy your API key (starts with `cwk-`)

## 1. v0 or Lovable?

#### Choose v0.dev when you want:

* **React/Next.js applications** with modern design
* **Quick iterations** and modern UI components
* **Vercel deployment** integration
* **shadcn/ui components** and modern patterns

#### Choose Lovable.dev when you want:

* **Full-stack applications** with complete backend/frontend
* **Complex multi-page applications**
* **Database integration** and user management
* **Multiple deployment options** (Vercel, Netlify, Railway)

## 2. Integration Methods

#### Method 1: v0.dev Premium (Automated)

If you have a **v0.dev premium account**, you can get automated integration:

1. **Get your v0.dev API key**:
   * Visit [v0.dev Chat Settings](https://v0.app/chat/settings/keys)
   * Create a new API key
2. **Go to Cody (the CodeWords chat) to store it securely by typing**:

> "Please store my v0.dev API key: v0\_1234567890abcdef..."

1. **Request automated generation**: The AI assistant will automatically create a v0.dev project with your CodeWords integration.

#### Method 2: Copy/Paste (for all users)

For **free v0.dev users** or **all Lovable.dev users**:

1. **Request a custom prompt**: Tell Cody about your preferred platform and ask for a tailored prompt

> Give me a custom prompt to input into Lovable to integrate with my CodeWords workflow as a back-end

2. **You should get a prompt that includes:**

* Complete service integration code
* UI/UX requirements
* Error handling
* Deployment instructions

3. **Copy and paste** the prompt into your chosen platform



### Example Integration Prompts

#### v0.dev Example (LinkedIn Enricher)

{% code overflow="wrap" %}
```
Create a professional React web interface for a LinkedIn Profile Enricher service. SERVICE OVERVIEW: This CodeWords service processes Google Spreadsheets containing LinkedIn profile URLs and enriches them with extracted profile data. UI REQUIREMENTS: - Clean, modern design with shadcn/ui components - Main form with Google Sheets ID input and processing options - Real-time progress indicator during enrichment - Results dashboard with success metrics and download links - Error handling with user-friendly feedback - Mobile-responsive layout CODEWORDS INTEGRATION: [Complete TypeScript integration code with your actual service details] REQUEST MODEL: { spreadsheet: string, include_email: boolean, output_columns: string[] } RESPONSE MODEL: { status: string, processed_count: number, success_rate: number, updated_sheet_url: string }
```
{% endcode %}

#### Lovable.dev Example (Full-Stack App)

{% code overflow="wrap" %}
```
Create a complete web application for LinkedIn Profile Enrichment: APPLICATION OVERVIEW: Build a professional web application that allows users to upload Google Sheets with LinkedIn URLs and get enriched profile data back. The app should feel like a modern SaaS tool. FRONTEND REQUIREMENTS: - Landing page explaining the service - Dashboard for managing enrichment jobs - File upload interface for Google Sheets - Real-time job monitoring with progress bars - Results page with data visualization - User account management - Mobile-responsive design BACKEND INTEGRATION: [Complete CodeWords integration setup with Node.js/Express] DATABASE: - Store job history and user preferences - Track usage analytics - Cache enrichment results
```
{% endcode %}

## 3. Once you have your prompt from Cody

#### Using v0.dev (Free Users)

1. Visit [v0.dev/chat](https://v0.dev/chat)
2. Paste the generated prompt
3. Refine the UI through conversation
4. Deploy using v0.dev's Vercel integration

#### Using Lovable.dev

1. Visit [lovable.dev](https://lovable.dev/)
2. Paste the generated prompt
3. Let Lovable generate the complete application
4. Customize and deploy using their platform options

## 4. Once deployed

1. Track the cost of your back-end on CodeWords
2. Make UI changes on your chosen UI platform
