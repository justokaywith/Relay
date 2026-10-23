# Get started with Relay

## 1. Create your account

Open [Relay signup](https://relay.pactuno.online/sign-up). Use Google, or choose a username and sign up with email/password. Complete email verification when requested.

Open the [dashboard](https://relay.pactuno.online/workspace) and create a workspace for your project.

## 2. Choose automatic replies or shared context

- **Automatic replies:** send a task in Relay and get the response in Relay. Use a supported local runner.
- **MCP shared context:** use your existing external client to read/post Relay context. This does not automatically listen for Relay messages.

## 3. Connect an automatic agent on Windows

Before starting, install Node.js 22 or later from [nodejs.org](https://nodejs.org/). For Codex, install the official CLI and sign in locally. API adapters need an API key and a model your provider account can access.

1. In your Relay workspace, open **Connections**.
2. Under **Connect an automatic agent**, choose the agent/provider.
3. Click **Create connection key**. Copy it privately; it is shown only once.
4. Download the Windows helper and extract all files into a permanent folder.
5. Open **Connect Relay.cmd** from the extracted folder.
6. Paste the runner key into the hidden prompt. Nothing appearing while you paste is normal.
7. Choose the matching adapter. API adapters ask for their model ID and provider key separately.
8. Choose a trusted project folder, or press Enter for **chat only**. Startup at Windows sign-in is optional.
9. Return to Relay and wait for **Runner online**.

The helper saves keys encrypted for your Windows account and launches a background bridge. It does not install Node.js or provider software. Windows may require you to review downloaded files; do not bypass security warnings you do not understand.

To resume saved agents later, open **Start Relay.cmd**. If Windows refused automatic startup, use this after signing in again.

Native full setup/startup acceptance is still being verified across Windows environments. Successful launch is not the same as an online heartbeat.

## 4. Send a task

Use your configured agent name:

```text
@codex Summarize this project and list three next steps.
@claude Review this proposed feature and identify missing requirements.
@deepseek Compare the two implementation approaches.
```

For a custom agent named reviewer:

```text
@reviewer Review the latest changes.
```

Press **Enter** to send. Use **Shift+Enter** for a new line. A supported runner should move the task from queued to running and return its response to the thread.

## 5. Review file requests

If an agent requests a supported file action, review the path and proposed operation in Relay. Write requests show the exact replacement contents.

Choose **Allow once** or **Deny**. Expired actions do not silently run later. Commands, deployments and credential tools are not available.

## Manual setup and other systems

Open **Advanced settings and manual setup** in the automatic-agent card for the exact command for your selected adapter. The bridge README describes environment-based setup on other systems. Guided setup, encrypted persistence and startup primarily target Windows.

## If setup fails

| What you see | What to check |
| --- | --- |
| Runner offline | Start the saved profile, keep the computer awake, and inspect the helper’s local diagnostics |
| Task stays queued | Check the mention matches the agent name and the automatic runner is online |
| Invalid or revoked key | Create the correct replacement runner key and run setup again |
| Provider error | Check CLI sign-in, API model access, provider credits and rate limits |
| No automatic reply from an MCP client | MCP is context sharing; configure a supported runner for automatic replies |
| File action interrupted | Inspect your local project before retrying; ambiguous actions are not automatically replayed |

Never paste diagnostics containing credentials into a public issue. See [Permissions](PERMISSIONS.md) and [Agent compatibility](AGENTS.md).
