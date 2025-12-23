---
hidden: true
---

# FAQs

### FAQs

#### General Questions

**Q: What is CodeWords and how does it work?**

**A:** CodeWords is a serverless automation platform that runs your Python workflows in secure, isolated sandboxes. You write FastAPI applications that can access AI models, third-party APIs, and automation tools. Each workflow runs on-demand without requiring server management.

**Q: Do I need to know specific frameworks to use CodeWords?**

**A:** Basic Python knowledge is required. Familiarity with FastAPI and Pydantic is helpful but not essential - the platform provides templates and examples to get you started quickly.

**Q: How much does CodeWords cost?**

**A:** CodeWords uses a pay-per-use model. You're charged for compute time, AI model usage, third-party API calls, and storage. There's a generous free tier to get started.

#### Development Questions

**Q: Can I use any Python package in my workflows?**

**A:** You can use most Python packages available on PyPI. Declare them in your workflow's PEP 723 header and they'll be automatically installed. Some packages with complex system dependencies might not be available.

**Q: How do I debug my workflows?**

**A:** Several debugging options:

* Use structured logging with `structlog`
* Stream logs in real-time during development
* Access detailed error traces
* Test locally before deployment
* Use the validation tool to catch issues early

**Q: Can workflows communicate with each other?**

**A:** Yes! Use the CodeWords client to call other workflows:

```python
async with AsyncCodewordsClient() as client:
    result = await client.run(
        service_id="other_workflow_id",
        data={"param": "value"}
    )
```

#### Integration Questions

**Q: How do I integrate with Google Sheets/Airtable?**

**A:** Use the native integration patterns:

* Google Sheets: OAuth token + Google Sheets API
* Airtable: API key + pyairtable library
* Both support batch operations for efficiency

**Q: What's the difference between Chrome Extension and Web Agent?**

**A:**

* **Chrome Extension**: Fast, simple browser automation. Good for data extraction and simple interactions.
* **Web Agent**: AI-powered automation for complex multi-step tasks. Handles dynamic content and complex workflows.

#### Security & Privacy Questions

**Q: How secure is my data in CodeWords?**

**A:** Security features include:

* Isolated sandbox execution (E2B)
* Encrypted secret storage
* No persistent storage between executions
* SOC 2 compliance (in progress)
* API key authentication

**Q: Can other users see my workflows or data?**

**A:** No. All workflows and data are private by default. You can optionally make workflows public as templates, but execution data remains private.

#### Performance Questions

**Q: What are the execution limits?**

**A:** Current limits:

* Maximum execution time: 15 minutes
* Memory limit: 2GB
* Storage: 10GB temporary
* Concurrent executions: 100 per user
* Rate limits vary by service

**Q: How can I optimize workflow performance?**

**A:** Best practices:

* Use concurrency with semaphores
* Batch API calls when possible
* Choose appropriate AI models for tasks
* Cache expensive computations
* Minimize data transfer

***

### Support & Resources

#### Documentation & Learning

* **Official Documentation**: [docs.codewords.ai](https://docs.codewords.ai/)
* **Video Tutorials**: [@agemohq](https://www.youtube.com/@agemohq)
* **Blog**: [agemo.ai/blog](https://agemo.ai/blog)

#### Community & Support

* **Discord Community**: Join our [discord.codewords.ai](https://discord.codewords.ai)
* **Support Email**: support@agemo.ai
* **Office Hours**: Weekly Q\&A sessions with the team _coming soon!_

#### Quick Links

* 🚀 **Platform**: [codewords.agemo.ai](https://codewords.agemo.ai)
* 📚 **Templates**: [codewords.agemo.ai/template-gallery](https://codewords.agemo.ai/template-gallery)
