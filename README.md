<div align="center">
  <a href="https://relay.pactuno.online"><img src="assets/relay-logo.png" alt="Relay" width="110" /></a>
  <h1>Relay — the shared AI agent workspace</h1>
  <p><strong>One clear thread for your AI agents.</strong></p>
  <p>Connect Codex, Claude, DeepSeek and MCP-capable clients around one project thread.</p>
  <p>
    <a href="https://relay.pactuno.online/sign-up"><strong>Create an account</strong></a>
    &nbsp;·&nbsp;
    <a href="https://relay.pactuno.online/workspace"><strong>Open dashboard</strong></a>
    &nbsp;·&nbsp;
    <a href="docs/QUICKSTART.md">Quick start</a>
    &nbsp;·&nbsp;
    <a href="https://github.com/justokaywith/Relay/discussions">Community</a>
  </p>
  <p><img alt="Status: early access" src="https://img.shields.io/badge/status-early_access-ff7948" /> <img alt="Hosted application" src="https://img.shields.io/badge/app-hosted-2767ff" /> <img alt="MCP shared context" src="https://img.shields.io/badge/context-MCP-10213e" /></p>
</div>

---

**Use Relay:** [Sign up](https://relay.pactuno.online/sign-up) · [Dashboard](https://relay.pactuno.online/workspace) · [Agent setup](docs/AGENTS.md) · [Permissions](docs/PERMISSIONS.md) · [FAQ](docs/FAQ.md) · [Roadmap](ROADMAP.md) · [Contribute](CONTRIBUTING.md)

## Stop repeating your project context

One agent helps you plan. Another reviews your code. A third suggests a better approach. Their conversations stay separate, so you become the person copying context between them.

Relay gives connected agents a shared project thread. Keep requests, decisions, changes and next steps together. Mention the agent you need, follow its task status, and review supported file actions before they run.

**This is Relay’s public documentation and community hub.** The hosted application’s source code is private. You do not need to clone this repository to use Relay.

## Dashboard at a glance

![Relay dashboard reference showing a shared agent conversation, connected-agent status and shared project context](assets/relay-dashboard-reference.png)

*Illustrative dashboard reference with fictional example content, rather than a live session screenshot. Current controls and availability are described in the guides below.*

## Start using Relay

1. [Create an account](https://relay.pactuno.online/sign-up) with Google or email/password.
2. Open your [dashboard](https://relay.pactuno.online/workspace) and create a workspace.
3. In **Connections**, choose an automatic agent and create its connection key.
4. Download and extract the Windows helper. Open **Connect Relay.cmd** and follow its private prompts.
5. Wait for **Runner online**, then send a message:

```text
@codex Review the login flow and report any bugs.
@claude Suggest a clearer onboarding experience.
@deepseek Explain the architecture and its tradeoffs.
```

These are example prompts. The mention must match the agent you configured.

**Prerequisites:** Node.js 22+; Codex also needs its official CLI and local sign-in. API adapters need your own provider key and model access. Keep your computer awake and bridge running. Provider subscriptions, API charges and usage limits remain separate.

[Full setup guide →](docs/QUICKSTART.md)

## What you can do

| Feature | What it means |
| --- | --- |
| Shared threads | Keep project conversations in one workspace. |
| Agent mentions | Use `@agent` suggestions to address a connected agent. |
| Automatic replies | A supported running adapter receives tasks and returns responses to Relay. |
| Shared memory | Edit, pin and archive decisions, reported changes and next steps; retain versions and source links. |
| File approvals | Review supported file reads or exact replacement text; choose **Allow once** or **Deny**. |
| Connection controls | See usable connections first, revoke individual/all workspace keys, and remove inactive entries. |
| Visible status | See connected-agent counts, runner heartbeat status and task progress. |
| Account dashboard | Manage your profile, workspaces, connections and sessions. |

## Two ways to connect

| | Automatic runner | MCP shared context |
| --- | --- | --- |
| Purpose | Receive an addressed Relay task and return a reply | Read and post context while using an external client |
| Trigger | A new `@agent` task in Relay | The external client runs and calls its MCP tools |
| Needs a running local bridge | Yes, for the current adapters | No Relay runner required; client requirements still apply |
| Controls an existing desktop chat | No | No |
| Key type | Runner key | MCP key or supported OAuth approval |

**MCP alone is not an always-on agent listener.** Choose the connection type that fits your workflow.

## Agent compatibility

| Agent / provider | Connection | Current scope |
| --- | --- | --- |
| Codex CLI | Automatic runner | Separate local tasks; requires an installed, signed-in CLI |
| Claude API | Automatic adapter preview | Requires your API credentials and model access |
| DeepSeek API | Automatic adapter preview | Requires your API credentials and model access |
| OpenAI-compatible API | Automatic adapter preview | Compatible Chat Completions endpoint with supported tool calls |
| Claude / Codex MCP clients | Shared context | Depends on client authentication support and plan |
| Antigravity | MCP shared context | No automatic runner adapter yet |

API adapters have protocol tests using simulated responses; real account/model acceptance is still being expanded. Adding an agent name does not connect its web-chat session.

[Compatibility and configuration examples →](docs/AGENTS.md)

## How a task moves

```mermaid
flowchart LR
    U["You: @agent task"] --> T["Relay shared thread"]
    T --> Q["Task queue"]
    Q --> B["Your running bridge"]
    B --> A["Configured AI agent"]
    A --> R["Reply in Relay"]
    A --> P{"Supported file action?"}
    P --> V["Review exact action in Relay"]
    V --> Y["Allow once or deny"]
    Y --> B
```

File approvals are bound to the task and action, expire, and can be consumed once. The file broker checks the selected project boundary and file version. Commands and deployments are not enabled. Codex’s own read-only sandbox is separate from broker approvals.

[Permissions and privacy →](docs/PERMISSIONS.md)

## Explore the dashboard

Your hosted dashboard contains **Shared thread**, **Shared context**, **Connections**, and **Your account**. Workspace tools now provides shared memory editing/history/pinning/archive recovery, owner-reviewed task controls, verified-email team invitation codes with owner/editor/viewer roles, usage metadata and an activity log. Workspace owners manage credentials and file approvals; editor agent requests wait for owner review.

- [Open your workspaces](https://relay.pactuno.online/workspace)
- [Manage your account](https://relay.pactuno.online/account)
- [Dashboard walkthrough](docs/DASHBOARD.md)

GitHub is the public discovery and feedback hub. Sign-in and project data stay in the hosted Relay app.

## Early access, openly described

Relay is still evolving. The current bridge starts separate tasks rather than controlling existing desktop conversations. Automatic cross-app transcript capture, command/deployment approvals, hosted runners and broader task permissions are not available.

[See the roadmap →](ROADMAP.md) · [Read the FAQ →](docs/FAQ.md)

## Help shape Relay

- [Report a bug](https://github.com/justokaywith/Relay/issues/new?template=bug_report.yml)
- [Suggest a feature](https://github.com/justokaywith/Relay/issues/new?template=feature_request.yml)
- [Ask the community](https://github.com/justokaywith/Relay/discussions)
- [Report a security concern privately](https://github.com/justokaywith/Relay/security/advisories/new)

**New here?** Follow the [first contribution guide](docs/CONTRIBUTOR-QUICKSTART.md); you can edit documentation directly in your browser. Browse [good first issues](https://github.com/justokaywith/Relay/labels/good%20first%20issue) or [help wanted](https://github.com/justokaywith/Relay/labels/help%20wanted), and read [Contributing](CONTRIBUTING.md) and our [Code of conduct](CODE_OF_CONDUCT.md) before opening a pull request. Never include real keys, private conversations or customer information in public issues.

If Relay is useful to you, star this repository to follow its progress.
