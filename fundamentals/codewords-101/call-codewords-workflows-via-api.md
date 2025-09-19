# Call CodeWords Workflows via API

### 1. Get Your API Key

First, obtain your API key from the [CodeWords Dashboard](https://codewords.agemo.ai/account/keys).

**API Key Types:**

* `cwk-` - Standard reusable keys (recommended)
* `cwotk-` - One-time keys (for sensitive operations)

### 2. Basic API Information

**Base URL:** `https://runtime.codewords.ai`

**Authentication:** Include this header in all requests:

```
codeAuthorization: Bearer YOUR_API_KEY_HERE
```

**Content Type:** Always use:

```
codeContent-Type: application/json
```

<figure><img src="../../.gitbook/assets/Area (1) (1).gif" alt=""><figcaption></figcaption></figure>

### 3. Synchronous API Calls (≤120 seconds)

Use for workflows that complete quickly (under 2 minutes).

#### cURL Example:

{% code overflow="wrap" %}
```bash
bash
curl -X POST https://runtime.codewords.ai/run/YOUR_SERVICE_ID \
  -H "Authorization: Bearer cwk-your-api-key-here" \
  -H "Content-Type: application/json" \
  -d '{ "input_field_1": "value1", "input_field_2": "value2" }'

```
{% endcode %}

#### Python Example:

{% code overflow="wrap" %}
```python
python
#Install: pip install codewords client 
import os from codewords_client 
import AsyncCodewordsClient 

async def call_workflow(): 
    async with AsyncCodewordsClient() as client: response = await client.run( service_id="your-service-id", inputs={ "input_field_1": "value1", "input_field_2": "value2" } ) response.raise_for_status() 
    return response.json() # Usage import asyncio result = asyncio.run(call_workflow()) print(result)
```
{% endcode %}

#### JavaScript/TypeScript Example:

{% code overflow="wrap" %}
```javascript
//Install: npm install @codewords/client 
import { createServiceClient } from "@codewords/client"; const client = createServiceClient(process.env.CODEWORDS_API_KEY); async function callWorkflow() { const result = await client.runService( "your-service-id", "", 
// path (empty for main endpoint) 
{ input_field_1: "value1", input_field_2: "value2" } ); return result; }
```
{% endcode %}

### 4. Asynchronous API Calls (>120 seconds)

Use for long-running workflows to avoid timeouts.

#### cURL Example:

{% code overflow="wrap" %}
```bash
# 1. Start async execution 
curl -X POST https://runtime.codewords.ai/run_async/YOUR_SERVICE_ID \ -H "Authorization: Bearer cwk-your-api-key-here" \ -H "Content-Type: application/json" \ -d '{"input_field": "value"}' 
# Response: {"request_id": "req_abc123def456"} 

# 2. Poll for results 
curl -X GET "https://runtime.codewords.ai/result/req_abc123def456" \ -H "Authorization: Bearer cwk-your-api-key-here" 

# 3. Stream logs (optional) 
curl -X GET "https://runtime.codewords.ai/logs/req_abc123def456" \ -H "Authorization: Bearer cwk-your-api-key-here" \ -H "Accept: text/event-stream"
```
{% endcode %}

#### Python Example:

{% code overflow="wrap" %}
```python
async def call_workflow_async(): async with AsyncCodewordsClient() as client: 
# Start async execution 
handle = await client.run( service_id="your-service-id", inputs={"input_field": "value"}, in_background=True ) print(f"Started: {handle.request_id}") 
# Wait for completion (10 minute timeout) 
response = await handle.result(timeout_seconds=600) return response.json()
```
{% endcode %}

#### JavaScript Example:

{% code overflow="wrap" %}
```javascript
async function callWorkflowAsync() { // Start async execution 
const requestId = await client.runAsync( "your-service-id", "", { input_field: "value" } ); console.log(`Started: ${requestId}`); 
// Poll for results (10 minute timeout) 
const result = await client.pollResult(600000); return result.responseJson; }
```
{% endcode %}

### 5. File Upload Workflow

For workflows that need file inputs:

#### cURL Example:

{% code overflow="wrap" %}
```bash
# 1. Create file upload 
curl -X POST "https://runtime.codewords.ai/file?filename=data.csv" \ -H "Authorization: Bearer cwk-your-api-key-here" 
# Response: {"upload_uri": "...", "download_uri": "..."} 

# 2. Upload file content 
curl -X PUT "UPLOAD_URI_FROM_STEP_1" \ -H "Content-Type: text/csv" \ -H "x-amz-acl: public-read" \ --data-binary @data.csv 

# 3. Use download URL in workflow call 
curl -X POST https://runtime.codewords.ai/run/your-service-id \ -H "Authorization: Bearer cwk-your-api-key-here" \ -H "Content-Type: application/json" \ -d '{"file_input": "DOWNLOAD_URI_FROM_STEP_1"}'
```
{% endcode %}

#### Python Example:

{% code overflow="wrap" %}
```python
async def upload_and_process_file(file_path: str): 
    async with AsyncCodewordsClient() as client: 
            file with open(file_path, 'rb') as f: 
                    file_content = f.read()
        download_url = await client.upload_file_content(filename="data.csv", file_content=file_content)    
        # Process with workflow 
        response = await client.run( service_id="your-service-id", inputs={"file_input": download_url} ) 
        return response.json()
```
{% endcode %}

### 6. Error Handling Best Practices

#### Handle Timeouts:

{% code overflow="wrap" %}
```python
try: response = await client.run(service_id="your-service", inputs=data) 
response.raise_for_status()
    return response.json()

except Exception as e: 
    if "504" in str(e) or "timeout" in str(e).lower(): 
        # Switch to async for long-running tasks 
        handle = await client.run(service_id="your-service", inputs=data, in_background=True)
        response = await handle.result(timeout_seconds=600) 
        return response.json() raise
```
{% endcode %}

#### Implement Retries:

{% code overflow="wrap" %}
```python
async def robust_call(service_id: str, inputs: dict, max_retries: int = 3): 
    for attempt in range(max_retries): 
        try: 
            async with AsyncCodewordsClient() as client: 
                response = await client.run(service_id=service_id, inputs=inputs) 
                response.raise_for_status() 
                return response.json() 
        except Exception as e: 
            if attempt == max_retries - 1: 
                raise await asyncio.sleep(2 ** attempt) # Exponential backoff
```
{% endcode %}

### 7. Environment Setup

**Set API Key as Environment Variable:**

Linux/Mac:

```bash
bashexport CODEWORDS_API_KEY=cwk-your-api-key-here
```

Windows:

```cmd
cmdset CODEWORDS_API_KEY=cwk-your-api-key-here
```

### 8. Security Best Practices

1. **Store API keys securely** as environment variables
2. **Never expose API keys** in client-side code
3. **Use HTTPS only** (CodeWords enforces this)
4. **Implement rate limiting** in your application
5. **Validate inputs** before sending to CodeWords
6. **Use one-time keys** for sensitive operations
7. **Rotate keys regularly** from the dashboard
