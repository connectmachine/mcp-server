<div align="center">

<img src="assets/logo-animated.gif" alt="ConnectMachine" width="112" height="112">

# ConnectMachine MCP Server

**Your contacts and digital business cards, inside any AI assistant.**

Search, update and organize your [ConnectMachine](https://connectmachine.ai) contacts, networks, events and cards in plain language from Claude, ChatGPT, Cursor, VS Code and any MCP client.

[![MCP Registry](https://img.shields.io/badge/MCP_Registry-ai.connectmachine-000000?style=flat-square&logo=modelcontextprotocol&logoColor=white)](https://registry.modelcontextprotocol.io/?q=ai.connectmachine)
[![Smithery](https://img.shields.io/badge/Smithery-cm--mcp-EA580C?style=flat-square)](https://smithery.ai/servers/connectmachine/cm-mcp)
[![Glama](https://img.shields.io/badge/Glama-mcp--server-7C3AED?style=flat-square)](https://glama.ai/mcp/servers/connectmachine/mcp-server)
[![Tools](https://img.shields.io/badge/tools-40-0F766E?style=flat-square)](#tools)
[![License](https://img.shields.io/badge/license-MIT-22C55E?style=flat-square)](LICENSE)

<br>

[![Add to Claude](https://img.shields.io/badge/Add_to-Claude-D97757?style=for-the-badge&logo=claude&logoColor=white)](https://claude.ai/directory/connectmachine)
[![Open in ChatGPT](https://img.shields.io/badge/Open_in-ChatGPT-10A37F?style=for-the-badge&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTIyLjI4MTkgOS44MjExYTUuOTg0NyA1Ljk4NDcgMCAwIDAtLjUxNTctNC45MTA4IDYuMDQ2MiA2LjA0NjIgMCAwIDAtNi41MDk4LTIuOUE2LjA2NTEgNi4wNjUxIDAgMCAwIDQuOTgwNyA0LjE4MThhNS45ODQ3IDUuOTg0NyAwIDAgMC0zLjk5NzcgMi45IDYuMDQ2MiA2LjA0NjIgMCAwIDAgLjc0MjcgNy4wOTY2IDUuOTggNS45OCAwIDAgMCAuNTExIDQuOTEwNyA2LjA1MSA2LjA1MSAwIDAgMCA2LjUxNDYgMi45MDAxQTUuOTg0NyA1Ljk4NDcgMCAwIDAgMTMuMjU5OSAyNGE2LjA1NTcgNi4wNTU3IDAgMCAwIDUuNzcxOC00LjIwNTggNS45ODk0IDUuOTg5NCAwIDAgMCAzLjk5NzctMi45MDAxIDYuMDU1NyA2LjA1NTcgMCAwIDAtLjc0NzUtNy4wNzI5em0tOS4wMjIgMTIuNjA4MWE0LjQ3NTUgNC40NzU1IDAgMCAxLTIuODc2NC0xLjA0MDhsLjE0MTktLjA4MDQgNC43NzgzLTIuNzU4MmEuNzk0OC43OTQ4IDAgMCAwIC4zOTI3LS42ODEzdi02LjczNjlsMi4wMiAxLjE2ODZhLjA3MS4wNzEgMCAwIDEgLjAzOC4wNTJ2NS41ODI2YTQuNTA0IDQuNTA0IDAgMCAxLTQuNDk0NSA0LjQ5NDR6bS05LjY2MDctNC4xMjU0YTQuNDcwOCA0LjQ3MDggMCAwIDEtLjUzNDYtMy4wMTM3bC4xNDIuMDg1MiA0Ljc4MyAyLjc1ODJhLjc3MTIuNzcxMiAwIDAgMCAuNzgwNiAwbDUuODQyOC0zLjM2ODV2Mi4zMzI0YS4wODA0LjA4MDQgMCAwIDEtLjAzMzIuMDYxNUw5Ljc0IDE5Ljk1MDJhNC40OTkyIDQuNDk5MiAwIDAgMS02LjE0MDgtMS42NDY0ek0yLjM0MDggNy44OTU2YTQuNDg1IDQuNDg1IDAgMCAxIDIuMzY1NS0xLjk3MjhWMTEuNmEuNzY2NC43NjY0IDAgMCAwIC4zODc5LjY3NjVsNS44MTQ0IDMuMzU0My0yLjAyMDEgMS4xNjg1YS4wNzU3LjA3NTcgMCAwIDEtLjA3MSAwbC00LjgzMDMtMi43ODY1QTQuNTA0IDQuNTA0IDAgMCAxIDIuMzQwOCA3Ljg3MnptMTYuNTk2MyAzLjg1NThMMTMuMTAzOCA4LjM2NCAxNS4xMTkyIDcuMmEuMDc1Ny4wNzU3IDAgMCAxIC4wNzEgMGw0LjgzMDMgMi43OTEzYTQuNDk0NCA0LjQ5NDQgMCAwIDEtLjY3NjUgOC4xMDQydi01LjY3NzJhLjc5Ljc5IDAgMCAwLS40MDctLjY2N3ptMi4wMTA3LTMuMDIzMWwtLjE0Mi0uMDg1Mi00Ljc3MzUtMi43ODE4YS43NzU5Ljc3NTkgMCAwIDAtLjc4NTQgMEw5LjQwOSA5LjIyOTdWNi44OTc0YS4wNjYyLjA2NjIgMCAwIDEgLjAyODQtLjA2MTVsNC44MzAzLTIuNzg2NmE0LjQ5OTIgNC40OTkyIDAgMCAxIDYuNjgwMiA0LjY2ek04LjMwNjUgMTIuODYzbC0yLjAyLTEuMTYzOGEuMDgwNC4wODA0IDAgMCAxLS4wMzgtLjA1NjdWNi4wNzQyYTQuNDk5MiA0LjQ5OTIgMCAwIDEgNy4zNzU3LTMuNDUzN2wtLjE0Mi4wODA1TDguNzA0IDUuNDU5YS43OTQ4Ljc5NDggMCAwIDAtLjM5MjcuNjgxM3ptMS4wOTc2LTIuMzY1NGwyLjYwMi0xLjQ5OTggMi42MDY5IDEuNDk5OHYyLjk5OTRsLTIuNTk3NCAxLjQ5OTctMi42MDY3LTEuNDk5N1oiLz48L3N2Zz4%3D)](https://chatgpt.com/plugins/plugin_asdk_app_6a68b263b2088191a0894900be991b07)
[![Install in Cursor](https://img.shields.io/badge/Install_in-Cursor-F2F2F2?style=for-the-badge&logo=cursor&logoColor=white)](https://cursor.com/install-mcp?name=connectmachine&config=eyJ1cmwiOiJodHRwczovL21jcC5jb25uZWN0bWFjaGluZS5haS9tY3AifQ%3D%3D)
[![Install in VS Code](https://img.shields.io/badge/Install_in-VS_Code-007ACC?style=for-the-badge&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTIzLjE1IDIuNTg3TDE4LjIxLjIxYTEuNDk0IDEuNDk0IDAgMCAwLTEuNzA1LjI5bC05LjQ2IDguNjMtNC4xMi0zLjEyOGEuOTk5Ljk5OSAwIDAgMC0xLjI3Ni4wNTdMLjMyNyA3LjI2MUExIDEgMCAwIDAgLjMyNiA4Ljc0TDMuODk5IDEyIC4zMjYgMTUuMjZhMSAxIDAgMCAwIC4wMDEgMS40NzlMMS42NSAxNy45NGEuOTk5Ljk5OSAwIDAgMCAxLjI3Ni4wNTdsNC4xMi0zLjEyOCA5LjQ2IDguNjNhMS40OTIgMS40OTIgMCAwIDAgMS43MDQuMjlsNC45NDItMi4zNzdBMS41IDEuNSAwIDAgMCAyNCAyMC4wNlYzLjkzOWExLjUgMS41IDAgMCAwLS44NS0xLjM1MnptLTUuMTQ2IDE0Ljg2MUwxMC44MjYgMTJsNy4xNzgtNS40NDh2MTAuODk2eiIvPjwvc3ZnPg%3D%3D)](https://vscode.dev/redirect/mcp/install?name=connectmachine&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.connectmachine.ai%2Fmcp%22%7D)

[Docs](https://www.connectmachine.ai/docs/mcp/) · [Setup](#set-up-your-client) · [Tools](#tools) · [Issues](https://github.com/connectmachine/mcp-server/issues)

</div>

---

## What you can ask

> *"Who did I meet at the Bangalore meetup last week that works in fintech?"*
>
> *"Find duplicates in my contacts and merge the obvious ones."*
>
> *"Import this CSV into a new network called Investors."*
>
> *"Tag everyone from today's conference with the event and draft a short follow-up for each."*
>
> *"Update my business card with my new title and LinkedIn."*

## Connect

The server is hosted. There is nothing to install or run yourself, and this repository holds only the registry manifest and documentation.

| | |
|---|---|
| **Endpoint** | `https://mcp.connectmachine.ai/mcp` |
| **Transport** | Streamable HTTP |
| **Auth** | OAuth 2.1 with Dynamic Client Registration and PKCE |
| **Account** | Any ConnectMachine account |

Your client discovers the OAuth settings on its own, so you never paste a token. The first time a tool runs, it opens the ConnectMachine sign-in page. Sign in with your email (one-time code) or Google, approve, and the tools are ready.

## Set up your client

<details>
<summary><b>Claude</b> (claude.ai, desktop and mobile)</summary>
<br>

Open [ConnectMachine in the Claude directory](https://claude.ai/directory/connectmachine) and select **Connect**.

Or add it yourself under **Settings → Connectors → Add custom connector** with the endpoint above.

</details>

<details>
<summary><b>Claude Code</b></summary>
<br>

```bash
claude mcp add --transport http connectmachine https://mcp.connectmachine.ai/mcp
```

Then run `/mcp` in Claude Code and pick **connectmachine** to sign in.

</details>

<details>
<summary><b>ChatGPT</b></summary>
<br>

Open [ConnectMachine in ChatGPT](https://chatgpt.com/plugins/plugin_asdk_app_6a68b263b2088191a0894900be991b07) and select **Connect**.

</details>

<details>
<summary><b>Cursor</b></summary>
<br>

Use the **Install in Cursor** button above, install the [ConnectMachine plugin](https://github.com/connectmachine/cursor-plugin), or add this to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "connectmachine": {
      "url": "https://mcp.connectmachine.ai/mcp"
    }
  }
}
```

</details>

<details>
<summary><b>VS Code and GitHub Copilot</b></summary>
<br>

Use the **Install in VS Code** button above, or add this to `.vscode/mcp.json`:

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

</details>

<details>
<summary><b>Cline</b></summary>
<br>

Add this to `cline_mcp_settings.json` (**MCP Servers → Configure → Configure MCP Servers**):

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

> [!IMPORTANT]
> Set `type` to `streamableHttp` exactly. Without it Cline falls back to SSE and the server answers `405`. See [llms-install.md](llms-install.md) for steps an agent can follow.

</details>

<details>
<summary><b>Gemini CLI</b></summary>
<br>

```bash
gemini extensions install https://github.com/connectmachine/mcp-server
```

Then run `/mcp auth connectmachine` inside Gemini CLI to sign in.

</details>

<details>
<summary><b>Any other client</b> (static key instead of OAuth)</summary>
<br>

If your client can't run the OAuth flow, sign in at <https://licenses.connectmachine.ai/mcp/auth> to get a personal MCP key. Send it as an `Authorization: Bearer <key>` header on the server entry. Keys don't expire.

</details>

## Tools

40 tools across six areas. Everything is scoped to your own account, and the server never reaches outside ConnectMachine, so every tool is annotated `openWorldHint: false`.

| Area | Tools | What it covers |
|---|:---:|---|
| [Contacts](#contacts) | 12 | Search, create, update, merge and de-duplicate contacts |
| [Networks](#networks) | 5 | Group contacts into labelled networks |
| [Events](#events) | 3 | Record where you met people |
| [Digital cards](#digital-cards) | 7 | Create and edit your business cards |
| [Import and export](#import-and-export) | 6 | Bulk import and CSV export |
| [Notifications and profile](#notifications-and-profile) | 7 | Notifications, profile and plan |

> [!NOTE]
> ⚠ marks tools annotated `destructiveHint: true`. They overwrite or remove data this server can't restore, so clients should confirm before calling them.

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

When two contacts share a name, `find_contact` reports the ambiguity and the assistant asks which one you mean instead of guessing.

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

## Registry

[`server.json`](server.json) is the manifest published to the [official MCP Registry](https://modelcontextprotocol.io/registry/about) under the DNS-verified `ai.connectmachine` namespace. The registry feeds downstream catalogs, including the [GitHub MCP Registry](https://github.com/mcp). [`gemini-extension.json`](gemini-extension.json) lists the server in the [Gemini CLI extension gallery](https://geminicli.com/extensions/).

## Docs and support

| | |
|---|---|
| Documentation | <https://www.connectmachine.ai/docs/mcp/> |
| Issues | <https://github.com/connectmachine/mcp-server/issues> |
| Terms | <https://www.connectmachine.ai/en/legal/terms-of-service> |
| Privacy | <https://www.connectmachine.ai/en/legal/privacy> |

<div align="center">
<br>
<sub>MIT licensed. See <a href="LICENSE">LICENSE</a>. Built by <a href="https://connectmachine.ai">ConnectMachine</a>.</sub>
</div>
