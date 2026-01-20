# Basic n8n AI Agent

This repo provides a minimal n8n workflow that exposes a webhook, sends user input to an AI agent, and returns the response.

## Files
- `basic-ai-agent.json` – workflow export for import into n8n

## Importing the Workflow
1. In n8n, select **Import** → **Import from File**.
2. Choose `basic-ai-agent.json`.
3. Assign an OpenAI credential to the **OpenAI Chat Model** node.
4. Activate the workflow.

## Request Example
Send a POST request to the webhook URL with a JSON body like this:

```json
{
  "chatInput": "Hello, AI!"
}
```

## Notes
This is intentionally minimal. You are expected to add your own production safeguards:
- Authentication/authorization for the webhook (it is unauthenticated by default).
- Rate limiting, abuse protection, and request size limits.
- Input validation and output filtering appropriate to your use case.
- Credentials in n8n (for example, an OpenAI credential on the **OpenAI Chat Model** node).

The AI agent expects `chatInput` at the root level; the **Format Input** node maps it from the request body.
