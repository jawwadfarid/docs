# Understanding CodeWords

#### Core Architecture

CodeWords is built on a **microservices architecture** where each workflow is a standalone FastAPI application that runs in secure, isolated sandboxes.

```mermaid
graph TB
    A[User Request] --> B[API Gateway]
    B --> C[Runtime Engine]
    C --> D[Sandbox Environment]
    D --> E[Your Workflow]
    E --> F[Response]
    
    G[Library Services] --> E
    H[AI Models] --> E
    I[Third-party APIs] --> E
```

#### Key Concepts

**1. Workflows**

* **FastAPI applications** that define your automation logic
* **Stateless** - each execution is independent
* **Scalable** - automatically handle concurrent requests
* **Versioned** - maintain multiple versions of your workflows

**2. Sandboxes**

* **Isolated environments** powered by E2B technology
* **Ephemeral** - created on-demand, destroyed after execution
* **Secure** - no access to other users' data or workflows
* **Resource-limited** - automatic cleanup and timeout protection

**3. Library Services**

Pre-built services that handle common tasks:

* **AI Models** - OpenAI, Anthropic, Gemini
* **Web Automation** - Chrome extension, web agents
* **Data Sources** - Reddit, GitHub, search engines
* **Communication** - Slack, WhatsApp, email
* **Storage** - File upload/download, state management

***

### Platform Components

#### 1. Runtime Engine

* **Request routing** and authentication
* **Sandbox provisioning** and lifecycle management
* **Dependency installation** using `uv`
* **Log streaming** and error handling
* **Usage tracking** and billing

#### 2. Library Services

**AI Services**

* **OpenAI GPT** (`openai`) - Text generation, embeddings, vision
* **Anthropic Claude** (`anthropic`) - Reasoning, analysis, tool use
* **Google Gemini** (`gemini`) - Large context, multimodal

**Web Automation**

* **Chrome Extension** (`chrome_extension`) - Browser automation
* **Web Agent** (`web_automation_agent`) - AI-powered web tasks
* **Webpage to Markdown** (`webpage_to_markdown`) - Content extraction

**Data Sources**

* **GitHub** (`github`) - Repository and profile search
* **Reddit** (`reddit`) - Post and comment retrieval
* **Search API** (`searchapi`) - Google, Bing, YouTube search
* **Hunter.io** (`hunter`) - Email finding

**Communication**

* **Slack Trigger** (`slack_trigger`) - Slack bot integration
* **WhatsApp Trigger** (`whatsapp_trigger`) - WhatsApp automation
* **Send Email** (`send_email`) - Email delivery

**Utilities**

* **Schedule Runs** (`schedule_runs`) - Workflow scheduling
* **User Login** (`user_login`) - Authentication management
* **Firecrawl** (`firecrawl`) - Web scraping

#### 3. Pipedream Integrations

Access 2000+ third-party services:

**Popular Categories**

* **CRM**: Salesforce, HubSpot, Pipedrive
* **Email**: Gmail, Outlook, Mailchimp
* **Calendar**: Google Calendar, Outlook Calendar
* **Social**: LinkedIn, Twitter, Facebook
* **Storage**: Google Drive, Dropbox, OneDrive
* **Payment**: Stripe, PayPal, Square
* **Database**: MySQL, PostgreSQL, MongoDB



***

### Integration Capabilities

CodeWords provides access to over **2,000+ third-party integrations** through Pipedream, enabling you to connect with virtually any tool in your tech stack:

**Popular Categories:**

* **CRM & Sales**: Salesforce, HubSpot, Pipedrive, Airtable, Monday.com
* **Communication**: Slack, Discord, Microsoft Teams, Zoom, WhatsApp
* **Email & Marketing**: Gmail, Outlook, Mailchimp, SendGrid, Constant Contact
* **Data & Analytics**: Google Sheets, Notion, Zapier, Snowflake, BigQuery
* **E-commerce**: Shopify, WooCommerce, Stripe, PayPal, Square
* **Social Media**: LinkedIn, Twitter, Facebook, Instagram, YouTube
* **Project Management**: Asana, Trello, Jira, Linear, ClickUp
* **Cloud Storage**: Google Drive, Dropbox, OneDrive, Box, AWS S3
* **Databases**: MySQL, PostgreSQL, MongoDB, Redis, Supabase
* **Developer Tools**: GitHub, GitLab, Docker, Jenkins, Vercel

**What This Means for You:**

* **No Integration Limits**: Access enterprise-grade APIs without worrying about rate limits or complex authentication
* **Unified Interface**: Use the same simple CodeWords syntax across all 2000+ services
* **OAuth Handled**: We manage authentication flows, tokens, and refreshes automatically
* **Enterprise Ready**: Connect to internal tools, databases, and custom APIs seamlessly

Whether you're building a simple automation or a complex multi-system workflow, CodeWords' extensive integration library ensures you can connect to the tools your organization already uses.

***

### Example Use Cases

#### Example 1: LinkedIn Profile Enricher

**Scenario**: Automatically enrich a list of LinkedIn URLs with structured profile data.

**Implementation**:

```python
# /// script
# requires-python = "==3.11.*"
# dependencies = [
#   "codewords-client==0.3.4",  # ✅ Updated from 0.2.4
#   "fastapi==0.116.1",         # ✅ Updated from 0.115.12
#   "uvicorn[standard]==0.35.0",
#   "pydantic==2.11.7",         # ✅ Updated from 2.11.3
#   "structlog==25.4.0"         # ✅ Updated from 25.2.0
# ]
# [tool.env-checker]
# env_vars = [
#   "PORT=8000",
#   "LOGLEVEL=INFO",
#   "CODEWORDS_API_KEY",
#   "CODEWORDS_RUNTIME_URI"
# ]
# ///

import asyncio
from typing import List, Optional
from fastapi import FastAPI, HTTPException
from pydantic import BaseModel, HttpUrl
from codewords_client import AsyncCodewordsClient, logger, run_service  # ✅ Correct imports

app = FastAPI(
    title="LinkedIn Profile Enricher",
    description="Enrich LinkedIn profile URLs with structured data"
)

class ProfileData(BaseModel):
    name: str
    headline: Optional[str] = None
    company: Optional[str] = None
    location: Optional[str] = None
    experience: List[str] = []
    education: List[str] = []

class EnrichmentRequest(BaseModel):
    linkedin_urls: List[HttpUrl]
    max_concurrent: int = 5

class EnrichmentResponse(BaseModel):
    profiles: List[ProfileData]
    success_count: int
    error_count: int

@app.post("/", response_model=EnrichmentResponse)
async def enrich_profiles(request: EnrichmentRequest):
    """Enrich LinkedIn profiles with structured data."""
    logger.info("Starting profile enrichment", url_count=len(request.linkedin_urls))
    
    semaphore = asyncio.Semaphore(request.max_concurrent)
    profiles = []
    errors = 0
    
    async def enrich_single_profile(url: str) -> Optional[ProfileData]:
        async with semaphore:
            try:
                # Use Chrome extension to scrape profile
                async with AsyncCodewordsClient() as client:
                    # Navigate to profile
                    result = await client.run(
                        service_id="chrome_extension",
                        inputs={  # ✅ Fixed: was path="/actions", data=
                            "actions": [
                                {"type": "navigate", "url": str(url)},
                                {"type": "wait", "time": 3},
                                {"type": "extract_html"}
                            ]
                        }
                    )
                    
                    result.raise_for_status()  # ✅ Added error checking
                    response_data = result.json()
                    
                    if not response_data.get("success"):
                        logger.error("Failed to extract profile", url=url)
                        return None
                    
                    html_content = response_data["data"]["html"]
                    
                    # Use AI to extract structured data  
                    ai_result = await client.run(
                        service_id="openai",
                        inputs={  # ✅ Fixed: was data=
                            "model": "gpt-4o-mini",
                            "prompt": f"Extract profile data from this HTML: {html_content}",
                            "example_output": ProfileData.model_json_schema()
                        }
                    )
                    
                    ai_result.raise_for_status()  # ✅ Added error checking
                    ai_response = ai_result.json()
                    return ProfileData(**ai_response["response"])
                    
            except Exception as e:
                logger.error("Error enriching profile", url=url, error=str(e))
                return None
    
    # Process all URLs concurrently
    tasks = [enrich_single_profile(str(url)) for url in request.linkedin_urls]
    results = await asyncio.gather(*tasks, return_exceptions=True)
    
    for result in results:
        if isinstance(result, ProfileData):
            profiles.append(result)
        else:
            errors += 1
    
    logger.info("Enrichment completed", success_count=len(profiles), error_count=errors)
    
    return EnrichmentResponse(
        profiles=profiles,
        success_count=len(profiles),
        error_count=errors
    )

if __name__ == "__main__":
    run_service(app)  # ✅ Fixed: was uvicorn.run(...)

```

**Try with a generated UI here:** [Scrape And Enrich Linkedin Post To Google Sheets](https://codewords.agemo.ai/run/scrape_and_enrich_linkedin_post_to_google_sheets)

OR

```bash
curl -X POST "https://your-workflow-url/" \
  -H "Content-Type: application/json" \
  -d '{
    "linkedin_urls": [
      "https://linkedin.com/in/johndoe",
      "https://linkedin.com/in/janedoe"
    ],
    "max_concurrent": 3
  }'
```

#### Example 2: Competitor Website Monitor

**Scenario**: Monitor competitor websites for changes and send Slack alerts.

**Implementation**:

```python
# /// script
# requires-python = "==3.11.*"
# dependencies = [
#   "codewords-client==0.3.4",  # ✅ Updated
#   "fastapi==0.116.1",         # ✅ Updated
#   "uvicorn[standard]==0.35.0",
#   "pydantic==2.11.7",         # ✅ Updated
#   "structlog==25.4.0"         # ✅ Updated
# ]
# [tool.env-checker]
# env_vars = [
#   "PORT=8000",
#   "LOGLEVEL=INFO", 
#   "CODEWORDS_API_KEY",
#   "CODEWORDS_RUNTIME_URI",
#   "PIPEDREAM_SLACK_ACCESS"     # ✅ Correct environment variable format
# ]
# ///

import os
from typing import Optional
from fastapi import FastAPI
from pydantic import BaseModel, HttpUrl
from codewords_client import AsyncCodewordsClient, logger, run_service  # ✅ Correct imports

app = FastAPI(
    title="Website Monitor",
    description="Monitor websites for changes and send alerts"
)

class MonitorRequest(BaseModel):
    url: HttpUrl
    slack_channel: str
    check_frequency: str = "0 9 * * *"  # ✅ Fixed cron syntax
    comparison_prompt: str = "Identify significant changes in content, pricing, or features"

class MonitorResponse(BaseModel):
    message: str
    changes_detected: bool
    summary: Optional[str] = None

@app.post("/", response_model=MonitorResponse)
async def monitor_website(request: MonitorRequest):
    """Monitor a website for changes and send alerts."""
    logger.info("Starting website monitoring", url=request.url)
    
    async with AsyncCodewordsClient() as client:
        # Get current website content
        current_content = await client.run(
            service_id="firecrawl",
            inputs={  # ✅ Fixed: was data=
                "url": str(request.url),
                "formats": ["markdown"],
                "onlyMainContent": True
            }
        )
        
        current_content.raise_for_status()  # ✅ Added error checking
        current_response = current_content.json()
        
        if not current_response.get("success"):
            logger.error("Failed to fetch website content")
            return MonitorResponse(
                message="Failed to fetch website content",
                changes_detected=False
            )
        
        current_markdown = current_response["data"]["markdown"]
        
        # Get previous snapshot from Redis
        snapshot_key = f"website_snapshot_{hash(str(request.url))}"
        
        redis_result = await client.run(
            service_id="redis_coordinator",
            inputs={  # ✅ Fixed: was data=
                "operation": "get",  # ✅ Fixed: was "action"
                "key": snapshot_key
            }
        )
        
        redis_result.raise_for_status()  # ✅ Added error checking
        redis_response = redis_result.json()
        previous_content = redis_response.get("value") if redis_response.get("success") else None
        
        if not previous_content:
            # First run - store snapshot
            await client.run(
                service_id="redis_coordinator",
                inputs={  # ✅ Fixed: was data=
                    "operation": "set",  # ✅ Fixed: was "action"
                    "key": snapshot_key,
                    "value": current_markdown,
                    "ttl": 30 * 24 * 3600  # ✅ Fixed: was 30  24  3600
                }
            )
            
            logger.info("Stored initial snapshot")
            return MonitorResponse(
                message="Initial snapshot stored. Monitoring will begin on next run.",
                changes_detected=False
            )
        
        # Compare content using AI
        comparison_result = await client.run(
            service_id="anthropic",
            inputs={  # ✅ Fixed: was data=
                "model": "claude-3-5-haiku-20241022",
                "prompt": f"""
                Compare these two versions of a website and {request.comparison_prompt}.
                
                Previous version:
                {previous_content}
                
                Current version:
                {current_markdown}
                
                Respond with a JSON object containing:
                - changes_detected: boolean
                - summary: string (if changes detected)
                """,
                "example_output": {
                    "changes_detected": True,
                    "summary": "Pricing increased from $99 to $129 for premium plan"
                }
            }
        )
        
        comparison_result.raise_for_status()  # ✅ Added error checking
        analysis = comparison_result.json().get("response", {})
        changes_detected = analysis.get("changes_detected", False)
        
        if changes_detected:
            summary = analysis.get("summary", "Changes detected")
            
            # Send Slack notification
            await client.run(
                service_id="pipedream",
                inputs={  # ✅ Fixed: was data=
                    "app": "slack",  # ✅ Fixed: was "app_slug"
                    "action": "send-message",  # ✅ Fixed: was "action_name"
                    "props": {
                        "channel": request.slack_channel,
                        "text": f"🚨 Website Change Detected!\n\n**URL**: {request.url}\n**Summary**: {summary}"
                    }
                }
            )
            
            # Update snapshot
            await client.run(
                service_id="redis_coordinator",
                inputs={  # ✅ Fixed: was data=
                    "operation": "set",  # ✅ Fixed: was "action"
                    "key": snapshot_key,
                    "value": current_markdown,
                    "ttl": 30 * 24 * 3600  # ✅ Fixed syntax
                }
            )
            
            logger.info("Changes detected and notification sent", summary=summary)
            
            return MonitorResponse(
                message="Changes detected and notification sent",
                changes_detected=True,
                summary=summary
            )
        else:
            logger.info("No significant changes detected")
            return MonitorResponse(
                message="No significant changes detected",
                changes_detected=False
            )

if __name__ == "__main__":
    run_service(app)  # ✅ Fixed: was uvicorn.run(...)

```

#### Example 3: AI-Powered Customer Support Ticket Analyzer

**Scenario**: Analyze support tickets, categorize them, and route to appropriate teams.

**Implementation**:

```python
# /// script
# requires-python = "==3.11.*"
# dependencies = [
#   "codewords-client==0.3.4",
#   "fastapi==0.116.1",
#   "uvicorn[standard]==0.35.0",
#   "pydantic==2.11.7",
#   "structlog==25.4.0"
# ]
# [tool.env-checker]
# env_vars = [
#   "PORT=8000",
#   "LOGLEVEL=INFO",
#   "CODEWORDS_API_KEY",
#   "CODEWORDS_RUNTIME_URI",
#   "PIPEDREAM_HUBSPOT_ACCESS"
# ]
# ///

from enum import Enum
from typing import List, Optional
from fastapi import FastAPI, HTTPException
from pydantic import BaseModel, Field
from codewords_client import AsyncCodewordsClient, logger, run_service

app = FastAPI(
    title="Support Ticket Analyzer",
    description="AI-powered support ticket analysis and routing"
)

class Priority(str, Enum):
    LOW = "low"
    MEDIUM = "medium"
    HIGH = "high"
    URGENT = "urgent"

class Category(str, Enum):
    BILLING = "billing"
    TECHNICAL = "technical"
    FEATURE_REQUEST = "feature_request"
    BUG_REPORT = "bug_report"
    GENERAL = "general"

class Sentiment(str, Enum):
    POSITIVE = "positive"
    NEUTRAL = "neutral"
    NEGATIVE = "negative"

class TicketAnalysis(BaseModel):
    category: Category
    priority: Priority
    sentiment: Sentiment
    summary: str = Field(description="Brief summary of the ticket")
    suggested_response: str = Field(description="Suggested response template")
    action_items: List[str] = Field(description="Specific action items")
    escalation_needed: bool = Field(description="Whether escalation is needed")

class AnalyzeTicketRequest(BaseModel):
    ticket_id: str
    subject: str
    content: str
    customer_email: str
    customer_tier: str = "standard"  # standard, premium, enterprise

class AnalyzeTicketResponse(BaseModel):
    ticket_id: str
    analysis: TicketAnalysis
    routing_team: str
    estimated_resolution_time: str

@app.post("/", response_model=AnalyzeTicketResponse)
async def analyze_ticket(request: AnalyzeTicketRequest):
    """Analyze a support ticket and provide routing recommendations."""
    logger.info("Starting ticket analysis", ticket_id=request.ticket_id)
    
    async with AsyncCodewordsClient() as client:
        # Analyze ticket using AI
        analysis_result = await client.run(
            service_id="openai",
            inputs={
                "model": "gpt-4o",
                "prompt": f"""
                Analyze this customer support ticket and provide detailed analysis:
                
                Customer Tier: {request.customer_tier}
                Subject: {request.subject}
                Content: {request.content}
                
                Consider:
                - Urgency indicators (downtime, revenue impact, security)
                - Customer tier (enterprise customers get higher priority)
                - Technical complexity
                - Sentiment and frustration level
                """,
                "example_output": TicketAnalysis.model_json_schema()
            }
        )
        
        analysis_result.raise_for_status()
        analysis_data = analysis_result.json()
        analysis = TicketAnalysis(**analysis_data["response"])
        
        # Determine routing team
        routing_team = determine_routing_team(analysis.category, analysis.priority, request.customer_tier)
        
        # Estimate resolution time
        resolution_time = estimate_resolution_time(analysis.category, analysis.priority, request.customer_tier)
        
        # Update CRM with analysis
        await update_crm_ticket(
            client,
            request.ticket_id,
            request.customer_email,
            analysis,
            routing_team
        )
        
        logger.info("Ticket analysis completed",
                   ticket_id=request.ticket_id,
                   category=analysis.category,
                   priority=analysis.priority,
                   team=routing_team)
        
        return AnalyzeTicketResponse(
            ticket_id=request.ticket_id,
            analysis=analysis,
            routing_team=routing_team,
            estimated_resolution_time=resolution_time
        )

def determine_routing_team(category: Category, priority: Priority, customer_tier: str) -> str:
    """Determine which team should handle the ticket."""
    if category == Category.BILLING:
        return "billing_team"
    elif category == Category.TECHNICAL and priority in [Priority.HIGH, Priority.URGENT]:
        return "senior_technical_team"
    elif category == Category.TECHNICAL:
        return "technical_team"
    elif category == Category.BUG_REPORT:
        return "engineering_team"
    elif category == Category.FEATURE_REQUEST:
        return "product_team"
    else:
        return "general_support_team"

def estimate_resolution_time(category: Category, priority: Priority, customer_tier: str) -> str:
    """Estimate resolution time based on ticket characteristics."""
    base_times = {
        Priority.URGENT: "2-4 hours",
        Priority.HIGH: "4-8 hours",
        Priority.MEDIUM: "1-2 days",
        Priority.LOW: "3-5 days"
    }
    
    # Enterprise customers get faster resolution
    if customer_tier == "enterprise":
        enterprise_times = {
            Priority.URGENT: "1-2 hours",
            Priority.HIGH: "2-4 hours",
            Priority.MEDIUM: "4-8 hours",
            Priority.LOW: "1-2 days"
        }
        return enterprise_times.get(priority, base_times[priority])
    
    return base_times.get(priority, "3-5 days")

async def update_crm_ticket(
    client: AsyncCodewordsClient,
    ticket_id: str,
    customer_email: str,
    analysis: TicketAnalysis,
    routing_team: str
):
    """Update CRM system with ticket analysis."""
    try:
        await client.run(
            service_id="pipedream",
            inputs={
                "app": "hubspot",
                "action": "update-ticket",
                "props": {
                    "ticket_id": ticket_id,
                    "properties": {
                        "hs_ticket_category": analysis.category,
                        "hs_ticket_priority": analysis.priority,
                        "sentiment": analysis.sentiment,
                        "routing_team": routing_team,
                        "ai_summary": analysis.summary,
                        "escalation_needed": analysis.escalation_needed
                    }
                }
            }
        )
        logger.info("CRM updated successfully", ticket_id=ticket_id)
    except Exception as e:
        logger.error("Failed to update CRM", ticket_id=ticket_id, error=str(e))

if __name__ == "__main__":
    run_service(app)

```

***

### Best Practices (Advanced)

#### 1. Workflow Design

**Structure Your Code Properly**

```python
# ✅ Good: Clear separation of concerns
class DataProcessor:
    async def process(self, data: list[dict]) -> list[dict]:
        cleaned = await self.clean_data(data)
        enriched = await self.enrich_data(cleaned)
        return await self.validate_results(enriched)
    
    async def clean_data(self, data: list[dict]) -> list[dict]:
        """Remove invalid entries and normalize formats."""
        return [item for item in data if self.is_valid_entry(item)]
    
    async def enrich_data(self, data: list[dict]) -> list[dict]:
        """Add additional information from external sources."""
        enriched = []
        async with AsyncCodewordsClient() as client:
            for item in data:
                enriched_item = await self.enrich_single_item(client, item)
                enriched.append(enriched_item)
        return enriched
    
    async def validate_results(self, data: list[dict]) -> list[dict]:
        """Validate final data quality."""
        return [item for item in data if self.meets_quality_threshold(item)]

# ❌ Bad: Everything in one function
@app.post("/")
async def process_everything(request):
    # 200 lines of mixed logic...
    pass

```

**Use Proper Error Handling**

```python
import asyncio
import httpx
from fastapi import HTTPException

# ✅ Good: Specific error handling with proper async patterns
async def make_api_call_with_retry(url: str, max_retries: int = 3) -> dict:
    """Make API call with exponential backoff retry."""
    async with httpx.AsyncClient() as client:
        for attempt in range(max_retries):
            try:
                response = await client.get(url, timeout=30.0)
                response.raise_for_status()
                return response.json()
            except httpx.HTTPStatusError as e:
                if e.response.status_code == 429:
                    # Handle rate limiting with exponential backoff
                    delay = 2 ** attempt
                    logger.warning("Rate limited, retrying", attempt=attempt + 1, delay=delay)
                    await asyncio.sleep(delay)
                    continue
                elif e.response.status_code >= 500:
                    # Server error - retry
                    if attempt == max_retries - 1:
                        raise HTTPException(status_code=502, detail="External service unavailable")
                    delay = 2 ** attempt
                    await asyncio.sleep(delay)
                    continue
                else:
                    # Client error - don't retry
                    raise HTTPException(status_code=e.response.status_code, detail="External API error")
            except httpx.TimeoutException:
                if attempt == max_retries - 1:
                    raise HTTPException(status_code=504, detail="Request timeout")
                await asyncio.sleep(2 ** attempt)
                continue
        
        raise HTTPException(status_code=502, detail="Max retries exceeded")

# ❌ Bad: Generic exception handling that hides problems
try:
    result = await external_api_call()
except Exception:
    return {"error": "Something went wrong"}  # Masks the real issue
    
```

**Implement Proper Logging**

```python
from codewords_client import logger

# ✅ Good: Structured logging with context
async def process_user_batch(users: list[dict], operation: str):
    logger.info("Starting batch processing", 
               batch_size=len(users),
               operation=operation)
    
    for i, user in enumerate(users):
        logger.info("Processing user", 
                   user_id=user.get("id"),
                   progress=f"{i+1}/{len(users)}")
        
        try:
            await process_single_user(user)
            logger.debug("User processed successfully", user_id=user.get("id"))
        except Exception as e:
            logger.error("Failed to process user", 
                        user_id=user.get("id"),
                        error=str(e))

# ❌ Bad: Basic print statements and unstructured logging
print(f"Processing {len(items)} items")
logging.info(f"Processing user {user_id}")  # String formatting loses structure

```

#### 2. Performance Optimization

**Use Concurrency Wisely**

```python
import asyncio

# ✅ Good: Controlled concurrency with proper error handling
async def process_items_concurrently(items: list[dict], max_concurrent: int = 5) -> list[dict]:
    """Process items concurrently with controlled rate limiting."""
    semaphore = asyncio.Semaphore(max_concurrent)
    results = []
    
    async def process_single_item(item: dict) -> dict | None:
        async with semaphore:
            try:
                return await expensive_operation(item)
            except Exception as e:
                logger.warning("Failed to process item", 
                             item_id=item.get("id"), 
                             error=str(e))
                return None
    
    # Process items concurrently
    tasks = [process_single_item(item) for item in items]
    raw_results = await asyncio.gather(*tasks, return_exceptions=True)
    
    # Filter out None results and exceptions
    results = [r for r in raw_results if r is not None and not isinstance(r, Exception)]
    
    logger.info("Batch processing completed", 
               total_items=len(items),
               successful=len(results),
               failed=len(items) - len(results))
    
    return results

# ❌ Bad: No concurrency control leads to rate limiting
async def process_items_sequentially(items: list[dict]):
    results = []
    for item in items:
        result = await expensive_operation(item)  # One at a time, very slow
        results.append(result)
    return results
    
```

**Optimize API Calls**

```python
# ✅ Good: Batch operations with proper async patterns
async def process_large_dataset(items: list[dict], batch_size: int = 10) -> list[dict]:
    """Process large datasets in optimized batches."""
    all_results = []
    total_batches = (len(items) + batch_size - 1) // batch_size
    
    for i in range(0, len(items), batch_size):
        batch = items[i:i + batch_size]
        batch_number = (i // batch_size) + 1
        
        logger.info("Processing batch", 
                   batch_number=batch_number,
                   total_batches=total_batches,
                   batch_size=len(batch))
        
        batch_results = await process_batch_with_retry(batch)
        all_results.extend(batch_results)
        
        # Add small delay between batches to be respectful to APIs
        if i + batch_size < len(items):
            await asyncio.sleep(0.5)
    
    return all_results

async def process_batch_with_retry(batch: list[dict]) -> list[dict]:
    """Process a batch with retry logic."""
    try:
        async with AsyncCodewordsClient() as client:
            result = await client.run(
                service_id="data_processor",
                inputs={"batch": batch}
            )
            result.raise_for_status()
            return result.json()["processed_items"]
    except Exception as e:
        logger.warning("Batch processing failed, retrying individual items", error=str(e))
        # Fall back to individual processing
        return await process_items_individually(batch)

async def process_items_individually(items: list[dict]) -> list[dict]:
    """Process items one by one as fallback."""
    results = []
    async with AsyncCodewordsClient() as client:
        for item in items:
            try:
                result = await client.run(
                    service_id="data_processor",
                    inputs={"item": item}
                )
                result.raise_for_status()
                results.append(result.json()["processed_item"])
            except Exception as e:
                logger.error("Failed to process individual item", 
                           item_id=item.get("id"), 
                           error=str(e))
    return results

# ❌ Bad: One item at a time without batching or error handling
async def process_inefficiently(items: list[dict]):
    for item in items:
        await process_single_item(item)  # Sequential, no error handling

```

#### 3. Security Best Practices

**Use Environment Variables for Secrets**

```python
import os
from fastapi import HTTPException

# ✅ Good: Environment variables with proper validation
def get_required_env_var(key: str) -> str:
    """Get required environment variable with clear error message."""
    value = os.environ.get(key)
    if not value:
        raise HTTPException(
            status_code=500, 
            detail=f"Required environment variable {key} is not set"
        )
    return value

# Usage in service
api_key = get_required_env_var("THIRD_PARTY_API_KEY")
database_url = get_required_env_var("DATABASE_URL")

# ❌ Bad: Hardcoded secrets (NEVER DO THIS)
api_key = "sk-1234567890abcdef"  # Never hardcode secrets!
database_url = "postgresql://user:pass@host:5432/db"  # Security risk!

# ❌ Bad: Silent failures with dummy defaults
api_key = os.environ.get("THIRD_PARTY_API_KEY", "dummy-key")  # Will fail later

```

**Validate Input Thoroughly**

```python
from pydantic import BaseModel, Field, field_validator, EmailStr
from typing import Literal

# ✅ Good: Comprehensive validation with proper types
class EmailRequest(BaseModel):
    email: EmailStr = Field(..., description="Valid email address")
    name: str = Field(..., min_length=1, max_length=100, description="Recipient name")
    age: int = Field(..., ge=0, le=120, description="Age in years")
    category: Literal["personal", "business"] = Field(..., description="Email category")
    
    @field_validator('name')
    @classmethod
    def validate_name(cls, v: str) -> str:
        """Validate and clean the name field."""
        name = v.strip()
        if not name:
            raise ValueError("Name cannot be empty")
        return name.title()

class ProcessingRequest(BaseModel):
    file_content: str = Field(..., max_length=1000000, description="File content to process")
    processing_type: Literal["extract", "summarize", "analyze"] = Field(..., description="Type of processing")
    
    @field_validator('file_content')
    @classmethod
    def validate_content(cls, v: str) -> str:
        """Validate file content is not empty and within size limits."""
        if not v.strip():
            raise ValueError("File content cannot be empty")
        if len(v.encode('utf-8')) > 5 * 1024 * 1024:  # 5MB limit
            raise ValueError("File content too large (max 5MB)")
        return v

# ❌ Bad: No validation allows invalid data through
class BadEmailRequest(BaseModel):
    email: str     # No validation - could be "not-an-email"
    name: str      # No validation - could be empty or 1000 chars
    age: int       # No validation - could be -50 or 999

```

#### 4. Cost Optimization

**Choose the Right AI Model**

```python
from codewords_client import AsyncCodewordsClient

def get_optimal_model_for_task(task_type: str, context_size: int = 0) -> str:
    """Select the most cost-effective model for the task."""
    if task_type == "simple_extraction" or context_size < 1000:
        return "gpt-4o-mini-2024-07-18"  # Cheapest for simple tasks
    elif task_type == "complex_reasoning" or context_size > 50000:
        return "gpt-4o-2024-11-20"  # More capable for complex tasks
    elif task_type == "large_context" or context_size > 100000:
        return "gemini-2.5-flash"  # Best for large inputs
    elif task_type == "critical_analysis":
        return "claude-sonnet-4-20250514"  # High quality reasoning
    else:
        return "gpt-4o-mini-2024-07-18"  # Default to cost-effective option

async def process_with_optimal_model(content: str, task_type: str) -> str:
    """Process content using the optimal model for the task."""
    model = get_optimal_model_for_task(task_type, len(content))
    
    logger.info("Selected AI model", model=model, task_type=task_type, content_length=len(content))
    
    async with AsyncCodewordsClient() as client:
        if model.startswith("gpt-") or model.startswith("o3-"):
            service_id = "openai"
        elif model.startswith("claude-"):
            service_id = "anthropic"
        elif model.startswith("gemini-"):
            service_id = "gemini"
        else:
            service_id = "openai"  # Default fallback
        
        result = await client.run(
            service_id=service_id,
            inputs={
                "model": model,
                "prompt": f"Process this content for {task_type}: {content}"
            }
        )
        result.raise_for_status()
        return result.json()["response"]

# ❌ Bad: Always using expensive models
async def expensive_processing(content: str) -> str:
    # Always uses the most expensive model regardless of task complexity
    return await process_with_model("claude-opus-4-20250514", content)

```

**Cache Expensive Operations**

```python
import json
from typing import Any, Optional

async def get_cached_result(cache_key: str, computation_func, ttl_seconds: int = 3600) -> Any:
    """Get result from cache or compute and cache it."""
    async with AsyncCodewordsClient() as client:
        # Try to get from cache first
        cache_result = await client.run(
            service_id="redis_coordinator",
            inputs={
                "operation": "get",
                "key": cache_key
            }
        )
        
        cache_result.raise_for_status()
        cache_data = cache_result.json()
        
        if cache_data.get("success") and cache_data.get("value"):
            logger.debug("Cache hit", cache_key=cache_key)
            return json.loads(cache_data["value"])
        
        # Cache miss - compute the result
        logger.debug("Cache miss, computing result", cache_key=cache_key)
        result = await computation_func()
        
        # Store in cache
        await client.run(
            service_id="redis_coordinator",
            inputs={
                "operation": "set",
                "key": cache_key,
                "value": json.dumps(result),
                "ttl": ttl_seconds
            }
        )
        
        logger.debug("Result cached", cache_key=cache_key, ttl=ttl_seconds)
        return result

# Usage example
async def expensive_analysis(text: str) -> dict:
    """Perform expensive AI analysis with caching."""
    cache_key = f"analysis_{hash(text)}"
    
    async def compute_analysis():
        async with AsyncCodewordsClient() as client:
            result = await client.run(
                service_id="openai",
                inputs={
                    "model": "gpt-4o",
                    "prompt": f"Analyze this text comprehensively: {text}"
                }
            )
            result.raise_for_status()
            return result.json()["response"]
    
    return await get_cached_result(cache_key, compute_analysis, ttl_seconds=7200)  # 2 hour cache

# ❌ Bad: No caching - repeats expensive operations
async def uncached_analysis(text: str) -> dict:
    # Always recomputes even for identical inputs
    async with AsyncCodewordsClient() as client:
        result = await client.run(
            service_id="openai",
            inputs={"model": "gpt-4o", "prompt": f"Analyze: {text}"}
        )
        return result.json()["response"]
        
```

***

