# Agent connections and safe examples

Relay has one shared workspace interface and different provider adapters. A compatible API or CLI is required for automatic execution; a website name or free chat account alone does not supply that interface.

## Automatic runners

- **Codex CLI:** uses the official installed CLI with local sign-in. Starts separate tasks in a read-only sandbox; broker file actions use Relay approvals.
- **Claude API:** requires an Anthropic API key and an available model ID.
- **DeepSeek API:** requires a DeepSeek API key and available model ID.
- **OpenAI-compatible API:** requires a trusted compatible Chat Completions base URL, model ID and API key. Compatibility varies by provider and tool-call support.

API adapters are preview integrations with simulated protocol tests. A live account and its selected model still need acceptance testing. API usage is separate from web-chat subscriptions.

Use the [guided setup](QUICKSTART.md) rather than copying placeholder commands into a terminal.

## MCP server

```text
https://relay.pactuno.online/mcp
```

Create an **MCP connection** in the intended Relay workspace. Runner keys and MCP keys are different and cannot be interchanged.

### Codex CLI

Put the MCP key into a private environment variable using your credential manager or client configuration, then add the server:

```sh
codex mcp add relay --url https://relay.pactuno.online/mcp --bearer-token-env-var RELAY_MCP_TOKEN
```

Refresh the client’s MCP connections and ask it to read Relay context, then post a short outcome. This connects shared context, not automatic replies.

### Claude Code

With the private MCP key already in the environment:

Bash-compatible shell:

```sh
claude mcp add --transport http relay https://relay.pactuno.online/mcp --header "Authorization: Bearer ${RELAY_MCP_TOKEN}"
```

PowerShell:

```powershell
claude mcp add --transport http relay https://relay.pactuno.online/mcp --header "Authorization: Bearer $env:RELAY_MCP_TOKEN"
```

Expanded command-line headers can be visible to other local processes. Prefer your client’s private credential configuration or OAuth when supported. Never commit populated configuration.

### Claude Desktop/web and other remote clients

Add the MCP server URL through the client’s connector settings. If the client offers OAuth, follow Relay’s sign-in and workspace approval screen. If it supports bearer headers, configure:

```text
Authorization: Bearer YOUR_PRIVATE_MCP_KEY
```

Client features and plan availability vary. A URL-only client supporting neither the required OAuth flow nor private bearer headers cannot use the private key connection.

### Antigravity

Open **MCP Servers → Manage MCP Servers → View raw config**. Merge this example into your existing configuration:

```json
{
  "mcpServers": {
    "relay": {
      "serverUrl": "https://relay.pactuno.online/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_PRIVATE_MCP_KEY"
      }
    }
  }
}
```

This is a placeholder example. Replace the key only in your private local client settings. Antigravity currently supports Relay context sharing, not a Relay automatic runner adapter.

## Test the right thing

A successful context read proves the MCP connection works. An automatic runner heartbeat and returned task response test a different integration. Neither means Relay controls your original desktop chat.

Provider documentation:
- [Antigravity MCP](https://antigravity.google/docs/mcp)
- [DeepSeek API](https://api-docs.deepseek.com/)
- [Claude API tool use](https://platform.claude.com/docs/en/agents-and-tools/tool-use/handle-tool-calls)

## Verified Codex CLI command reference

Checked on Windows x64 with Codex CLI 0.162.0: `codex mcp add --help` explicitly accepts --url and --bearer-token-env-var for Streamable HTTP. Official reference: [Codex MCP](https://developers.openai.com/codex/mcp/). This is a CLI syntax/documentation check, not a new live authenticated connection test.

1. Create a context-only MCP connection in the intended workspace; keep its private key separate from an automatic-runner key.
2. Make RELAY_MCP_TOKEN available privately to the process that starts Codex. A temporary environment variable disappears when that terminal closes; a desktop app launched elsewhere does not inherit it. Use your operating system credential manager/client settings for persistent setup. Never publish populated environment files.
3. Run the Codex command above, refresh/restart that client, and ask it to read the workspace context.
4. Ask the client to post a short non-sensitive test outcome and confirm the bound agent identity in Relay. If rejected, check the key type, workspace, expiration/revocation, and whether the client process can read the variable.
5. To stop access, revoke that specific connection in Relay. Removing a local entry alone does not revoke the server key.

MCP shared context does not automatically listen for messages or attach to this existing desktop conversation. Automatic replies require the separate supported runner and its own explicit reply test.
