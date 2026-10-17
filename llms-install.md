# Installing the ConnectMachine MCP server

ConnectMachine is a hosted, remote MCP server. There is nothing to clone, build or run locally.

- Endpoint: `https://mcp.connectmachine.ai/mcp`
- Transport: Streamable HTTP
- Auth: OAuth 2.1 with Dynamic Client Registration and PKCE, discovered automatically from the server's `WWW-Authenticate` challenge and `/.well-known/oauth-protected-resource/mcp`

## Steps for Cline

1. Open the MCP settings file: MCP Servers → Configure → Configure MCP Servers (`cline_mcp_settings.json`).
2. Add this entry under `mcpServers`, keeping any existing servers:

   ```json
   {
     "mcpServers": {
       "connectmachine": {
         "type": "streamableHttp",
         "url": "https://mcp.connectmachine.ai/mcp"
       }
     }
   }
   ```

   `type` must be exactly `streamableHttp`. A missing or misspelled `type` makes Cline use SSE, and the server answers 405.
3. Save the file. Cline connects and opens the ConnectMachine sign-in page in the browser.
4. The user signs in with their ConnectMachine account (email code or Google) and approves access. Any account works, including free ones.
5. Confirm the connection by calling `get_profile`. It returns the signed-in user's profile.

No API keys, environment variables or dependencies are needed.

## If OAuth isn't available

A client that can't do OAuth can use a personal MCP key instead: the user signs in at <https://licenses.connectmachine.ai/mcp/auth>, copies the key, and the client sends it as a header:

```json
{
  "mcpServers": {
    "connectmachine": {
      "type": "streamableHttp",
      "url": "https://mcp.connectmachine.ai/mcp",
      "headers": { "Authorization": "Bearer <MCP key>" }
    }
  }
}
```

## Try it

- "Which founders do I know in fintech?"
- "Save Sara Khan, fintech founder, met at WebSummit."
- "Draft follow-ups to the people I met last week."
