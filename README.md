# ConnectMachine MCP Server

[![MCP Registry](https://img.shields.io/badge/MCP_Registry-ai.connectmachine-000000?logo=modelcontextprotocol&logoColor=white)](https://registry.modelcontextprotocol.io/?q=ai.connectmachine)
[![Smithery](https://img.shields.io/badge/Smithery-connectmachine%2Fcm--mcp-EA580C)](https://smithery.ai/servers/connectmachine/cm-mcp)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

Connect your AI assistant to [ConnectMachine](https://connectmachine.ai), the
digital business-card and contact platform. Manage contacts, events, networks,
and your digital cards in natural language.

This repository holds the public registry manifest and documentation for the
hosted server. The server itself runs at `https://mcp.connectmachine.ai/mcp`
— there is nothing to install or self-host.

## Connect

| | |
|---|---|
| Endpoint | `https://mcp.connectmachine.ai/mcp` |
| Transport | Streamable HTTP |
| Auth | OAuth 2.1 with Dynamic Client Registration and PKCE |

Your client discovers the OAuth configuration automatically, so you never paste
a token by hand. On first use it opens the ConnectMachine sign-in page; sign in
with your account email (one-time code) or Google, and approve.

Requires a ConnectMachine account with onboarding completed in the app.

### Claude

[![Add to Claude](https://img.shields.io/badge/Add_to_Claude-Custom_Connector-D97757?logo=claude&logoColor=white)](https://www.connectmachine.ai/docs/mcp/)

Add it under Settings → Connectors → Add custom connector, using the endpoint
above.

### Cursor

[![Install MCP Server](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=connectmachine&config=eyJ1cmwiOiJodHRwczovL21jcC5jb25uZWN0bWFjaGluZS5haS9tY3AifQ%3D%3D)

Install the [ConnectMachine plugin](https://github.com/connectmachine/cursor-plugin),
or add the server to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "connectmachine": {
      "url": "https://mcp.connectmachine.ai/mcp"
    }
  }
}
```

### VS Code and GitHub Copilot

[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install_Server-0098FF?logo=githubcopilot&logoColor=white)](https://vscode.dev/redirect/mcp/install?name=connectmachine&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.connectmachine.ai%2Fmcp%22%7D)

Add the server to `.vscode/mcp.json`:

```json
{
  "servers": {
    "connectmachine": {
      "type": "http",
      "url": "https://mcp.connectmachine.ai/mcp"
    }
  }
}
```

### Static key instead of OAuth

If your client cannot do the OAuth flow, sign in at
<https://licenses.connectmachine.ai/mcp/auth> to get a personal MCP key, then
send it as an `Authorization: Bearer <key>` header on the server entry. Keys do
not expire.

## Tools

48 tools across ten areas. Everything is scoped to your own account — the
server never reaches outside ConnectMachine, so every tool is annotated
`openWorldHint: false`.

### Contacts

| Tool | Kind | What it does |
|---|---|---|
| `list_contacts` | read | List contacts with pagination and filters |
| `get_contact` | read | Full details for one contact |
| `search_contacts` | read | Search across name, company, title, email, phone, notes, location, events |
| `find_contact` | read | Resolve a name to one contact, or report an ambiguity |
| `list_industries` | read | The industry catalog used for filtering |
| `get_contact_counts` | read | Contact counts broken down by source |
| `get_duplicate_contacts` | read | Surface suspected duplicates without merging |
| `create_contact` | write | Create a contact, optionally tagged with events |
| `update_contact` | write ⚠ | Overwrite fields on an existing contact |
| `delete_contacts` | write ⚠ | Permanently remove contacts |
| `merge_contacts` | write ⚠ | Merge duplicates; the secondary record is removed |
| `assign_contacts_to_network` | write ⚠ | Move contacts into a network |

When two contacts share a name, `find_contact` reports the ambiguity and the
assistant asks which one you mean rather than guessing.

### Networks

| Tool | Kind | What it does |
|---|---|---|
| `list_networks` | read | List your networks (labels) |
| `create_network` | write | Create a network |
| `update_network` | write ⚠ | Rename or restyle a network |
| `delete_network` | write ⚠ | Remove a network |
| `reorder_networks` | write ⚠ | Change network ordering |

### Events

| Tool | Kind | What it does |
|---|---|---|
| `list_events` | read | Conferences and meetups where you met contacts |
| `add_events_to_contact` | write | Tag a contact with where you met them |
| `remove_events_from_contact` | write ⚠ | Detach events from a contact |

### Digital cards

| Tool | Kind | What it does |
|---|---|---|
| `list_cards` | read | List your business cards |
| `get_card` | read | Full details for one card |
| `get_shared_card` | read | Resolve a public share link to card data |
| `read_card_image` | read | Read a card's image asset |
| `create_card` | write | Create a card with emails, phones, websites, socials |
| `update_card` | write ⚠ | Overwrite fields on a card |
| `delete_card` | write ⚠ | Remove a card |

### AI and meetings

| Tool | Kind | What it does |
|---|---|---|
| `ai_query` | read | Ask a natural-language question about your network |
| `list_ai_templates` | read | Prebuilt query templates |
| `event_meeting_transcript_qa` | read | Q&A over event and meeting transcripts |
| `list_transcriptions` | read | List meeting transcriptions |
| `get_transcription` | read | Fetch one transcription |
| `get_meeting_action_items` | read | Action items extracted from a meeting |
| `generate_meeting_action_items` | write | Generate action items for a meeting |
| `delete_transcription` | write ⚠ | Remove a transcription |

### Import and export

| Tool | Kind | What it does |
|---|---|---|
| `get_import_status` | read | Progress of an import session |
| `list_import_sessions` | read | All import sessions |
| `export_contacts_csv` | read | Export contacts to CSV (Premium) |
| `create_import_session` | write | Start an import batch |
| `import_contacts_batch` | write | Import up to 500 contacts per call |
| `abort_import` | write ⚠ | Cancel an in-progress import |

### Notifications and profile

| Tool | Kind | What it does |
|---|---|---|
| `list_notifications` | read | List notifications |
| `get_unread_count` | read | Unread notification count |
| `get_profile` | read | Your ConnectMachine profile |
| `get_subscription_status` | read | Plan and subscription status |
| `get_enrichment_data` | read | Profile completion suggestions |
| `mark_notification_read` | write ⚠ | Mark one notification read |
| `mark_all_notifications_read` | write ⚠ | Mark every notification read |

⚠ marks tools annotated `destructiveHint: true` — they overwrite or remove data
that this server cannot restore. Clients are expected to confirm before calling
them.

## Registry

`server.json` is the manifest published to the
[official MCP Registry](https://modelcontextprotocol.io/registry/about), which
feeds downstream catalogs including the
[GitHub MCP Registry](https://github.com/mcp). It is published under the
`ai.connectmachine` namespace, verified by DNS.

## Docs and support

- Documentation: <https://www.connectmachine.ai/docs/mcp/>
- Issues: <https://github.com/connectmachine/mcp-server/issues>
- Terms: <https://www.connectmachine.ai/en/legal/terms-of-service>
- Privacy: <https://www.connectmachine.ai/en/legal/privacy>

## License

MIT — see [LICENSE](LICENSE).
