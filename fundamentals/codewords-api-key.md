---
icon: key-skeleton
---

# CodeWords API key

The CodeWords API lets any external application trigger your workflows with simple HTTP requests. Whether you're building a web app, mobile app, or connecting to third-party services, it's as easy as making a POST request.

### Getting your API key

First things first — you'll need credentials. Grab your API key from the [Codewords account dashboard](https://codewords.agemo.ai/account/keys).

Your API key will be under the **Your API keys section**:

* `cwk-` for standard reusable keys (most common)
* `cwotk-` for one-time keys (extra security for sensitive operations)

Pro tip: Treat your API key like a password — keep it secret and store it as an environment variable.

<figure><img src="../.gitbook/assets/apikey.gif" alt=""><figcaption></figcaption></figure>

### How the API works

Base URL: `https://runtime.codewords.ai`

The endpoints you'll use:

* Quick tasks: `POST /run/{serviceId}` (under two minutes)
* Heavy lifting: `POST /run_async/{serviceId}` (up to 30 minutes)
* Check results: `GET /result/{request_id}` (for async calls)
* Watch progress: `GET /logs/{request_id}` (live streaming)
* Upload files: `POST /file` (when your workflow needs files)

Authentication: Just add `Authorization: Bearer {YOUR_API_KEY}` to your headers.

### Quick synchronous calls

Perfect for automations that finish fast (under two minutes). Your request waits for the result and gets it back immediately.

#### Using cURL

```bash
# Basic call to a LinkedIn enricher
curl -X POST https://runtime.codewords.ai/run/linkedin-enricher \
  -H "Authorization: Bearer cwk-your-api-key-here" \
  -H "Content-Type: application/json" \
  -d '{
    "spreadsheet": "1BxiMVs0XRA5nFMdKvBdBZjgmUUqptlbs74OgvE2upms",
    "include_email": false,
    "output_columns": ["bio", "location", "current_job"]
  }'

# Success response:
# {
#   "status": "completed",
#   "processed_count": 25,
#   "success_rate": 0.92,
#   "updated_sheet_url": "https://docs.google.com/spreadsheets/d/...",
#   "summary": "## Enrichment Complete\n\n✅ **25 profiles processed**..."
# }

# If it takes too long:
# HTTP 504 Gateway Timeout (switch to async!)
```

#### Python example

Install the CodeWords client first:

```bash
pip install codewords-client
```

```python
import os
from codewords_client import AsyncCodewordsClient
import asyncio

# Set your API key as environment variable
# export CODEWORDS_API_KEY=cwk-your-api-key-here

async def enrich_linkedin_profiles(spreadsheet_id: str):
    """Call the LinkedIn enricher and get results back immediately."""
    
    async with AsyncCodewordsClient() as client:
        try:
            response = await client.run(
                service_id="linkedin-enricher",
                inputs={
                    "spreadsheet": spreadsheet_id,
                    "include_email": False,
                    "output_columns": ["bio", "location", "current_job"]
                }
            )
            response.raise_for_status()
            return response.json()
            
        except Exception as e:
            if "504" in str(e) or "timeout" in str(e).lower():
                raise TimeoutError("Service took too long - try async instead")
            raise

# Usage
async def main():
    try:
        result = await enrich_linkedin_profiles("1BxiMVs0XRA5nFMdKvBdBZjgmUUqptlbs74OgvE2upms")
        print(f"Processed {result['processed_count']} profiles")
        print(f"Success rate: {result['success_rate']:.1%}")
    except TimeoutError:
        print("That took too long - consider using async execution")

asyncio.run(main())
```

#### JavaScript/TypeScript example

Install the client:

```bash
npm install @codewords/client
```

```typescript
import { createServiceClient } from "@codewords/client";

// Set your API key as environment variable
const client = createServiceClient(process.env.CODEWORDS_API_KEY!);

interface LinkedInRequest {
  spreadsheet: string;
  include_email: boolean;
  output_columns: string[];
}

async function enrichLinkedInProfiles(request: LinkedInRequest) {
  try {
    const result = await client.runService(
      "linkedin-enricher", // service ID
      "",                  // path (empty for main endpoint)
      request              // your data
    );
    
    return result;
  } catch (error) {
    if (error.response?.status === 504) {
      throw new Error("Service timed out - try async execution");
    }
    throw error;
  }
}

// Usage
const request = {
  spreadsheet: "1BxiMVs0XRA5nFMdKvBdBZjgmUUqptlbs74OgvE2upms",
  include_email: false,
  output_columns: ["bio", "location", "current_job"]
};

const result = await enrichLinkedInProfiles(request);
console.log(`Processed ${result.processed_count} profiles`);
```

### Asynchronous calls for heavy lifting

For automations that need more time (up to 30 minutes), use async execution. You'll get a request ID immediately, then check back for results.

#### Using cURL

```bash
# 1. Start the async job
curl -X POST https://runtime.codewords.ai/run_async/linkedin-enricher \
  -H "Authorization: Bearer cwk-your-api-key-here" \
  -H "Content-Type: application/json" \
  -d '{
    "spreadsheet": "1BxiMVs0XRA5nFMdKvBdBZjgmUUqptlbs74OgvE2upms",
    "include_email": true,
    "output_columns": ["bio", "location", "current_job", "education"]
  }'

# Response: {"request_id": "req_abc123def456"}

# 2. Check if it's done (might return 408 if still running)
curl -X GET "https://runtime.codewords.ai/result/req_abc123def456" \
  -H "Authorization: Bearer cwk-your-api-key-here"

# Not ready: HTTP 408 Request Timeout
# Ready: Full result with status 200

# 3. Optional: Watch live logs
curl -X GET "https://runtime.codewords.ai/logs/req_abc123def456" \
  -H "Authorization: Bearer cwk-your-api-key-here" \
  -H "Accept: text/event-stream"
```

#### Python example

```python
from codewords_client import AsyncCodewordsClient
import asyncio

async def enrich_profiles_async(spreadsheet_id: str):
    """Start a big job and wait for it to finish."""
    
    async with AsyncCodewordsClient() as client:
        # Start the job in background
        handle = await client.run(
            service_id="linkedin-enricher",
            inputs={
                "spreadsheet": spreadsheet_id,
                "include_email": True,
                "output_columns": ["bio", "location", "current_job", "education"]
            },
            in_background=True  # This makes it async
        )
        
        print(f"Started background job: {handle.request_id}")
        
        # Wait for it to finish (up to 10 minutes)
        response = await handle.result(timeout_seconds=600)
        return response.json()

# Usage
async def main():
    result = await enrich_profiles_async("1BxiMVs0XRA5nFMdKvBdBZjgmUUqptlbs74OgvE2upms")
    print(f"Async job completed!")
    print(f"Processed {result['processed_count']} profiles")

asyncio.run(main())
```

#### TypeScript example

```typescript
import { createServiceClient } from "@codewords/client";

const client = createServiceClient(process.env.CODEWORDS_API_KEY!);

async function enrichProfilesAsync(request: LinkedInRequest) {
  // Start async execution
  const requestId = await client.runAsync(
    "linkedin-enricher",
    "",
    request
  );
  
  console.log(`Started async job: ${requestId}`);
  
  // Wait for results (10 minutes max)
  const result = await client.pollResult(600000);
  
  if (result.responseStatus === 200) {
    return result.responseJson;
  } else {
    throw new Error(`Job failed with status ${result.responseStatus}`);
  }
}
```

### Working with files

When your CodeWords automation needs file inputs, upload them first and pass the download URLs.

#### Upload and process pattern

```python
from codewords_client import AsyncCodewordsClient

async def process_my_csv(file_path: str):
    """Upload a local file and process it with CodeWords."""
    
    async with AsyncCodewordsClient() as client:
        # Read your local file
        with open(file_path, 'rb') as f:
            file_content = f.read()
        
        # Upload to CodeWords
        download_url = await client.upload_file_content(
            filename="data.csv",
            file_content=file_content
        )
        
        # Process with your automation
        response = await client.run(
            service_id="csv-processor",
            inputs={
                "csv_file": download_url,
                "processing_options": {"header_row": True}
            }
        )
        return response.json()

# Usage
result = await process_my_csv("./my-data.csv")
print(f"Processed {result['row_count']} rows")
```

### Integrating with web apps

Here's how to add CodeWords to a Flask web application:

```python
from flask import Flask, request, jsonify
from codewords_client import AsyncCodewordsClient
import asyncio

app = Flask(__name__)

@app.route('/analyze-spreadsheet', methods=['POST'])
def analyze_spreadsheet():
    """API endpoint that calls CodeWords behind the scenes."""
    
    data = request.get_json()
    spreadsheet_id = data.get('spreadsheet_id')
    
    if not spreadsheet_id:
        return jsonify({"error": "spreadsheet_id required"}), 400
    
    async def call_codewords():
        async with AsyncCodewordsClient() as client:
            response = await client.run(
                service_id="linkedin-enricher",
                inputs={
                    "spreadsheet": spreadsheet_id,
                    "include_email": False,
                    "output_columns": ["bio", "location", "current_job"]
                }
            )
            return response.json()
    
    try:
        result = asyncio.run(call_codewords())
        return jsonify(result)
    except Exception as e:
        if "timeout" in str(e).lower():
            return jsonify({"error": "Analysis timed out"}), 408
        return jsonify({"error": str(e)}), 500

if __name__ == '__main__':
    app.run(debug=True)
```

### Error handling best practices

Make your API calls bulletproof with smart retry logic:

```python
from codewords_client import AsyncCodewordsClient
import asyncio
import logging

async def bulletproof_call(
    service_id: str, 
    inputs: dict, 
    max_retries: int = 3
):
    """Make a robust call with automatic retry and timeout handling."""
    
    async with AsyncCodewordsClient() as client:
        for attempt in range(max_retries):
            try:
                # Try sync first
                response = await client.run(
                    service_id=service_id,
                    inputs=inputs
                )
                return response.json()
                
            except Exception as e:
                if "timeout" in str(e).lower() or "504" in str(e):
                    # Switch to async for timeouts
                    logging.info("Switching to async mode due to timeout...")
                    handle = await client.run(
                        service_id=service_id,
                        inputs=inputs,
                        in_background=True
                    )
                    response = await handle.result(timeout_seconds=600)
                    return response.json()
                
                # Retry on other errors
                if attempt < max_retries - 1:
                    await asyncio.sleep(2 ** attempt)  # Exponential backoff
                    continue
                raise

# Usage
try:
    result = await bulletproof_call("my-automation", {"input": "data"})
    print("Success!")
except Exception as e:
    print(f"Failed after retries: {e}")
```

\
