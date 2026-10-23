# Frequently asked questions

### Do I install Relay from this repository?

No. This repository is a public documentation/community hub. Open [Relay](https://relay.pactuno.online) to create an account. Application source and a self-hosted distribution are not published here.

### Can multiple people sign up?

Yes, users can register separate accounts and create their own workspaces. Shared team membership and roles are not implemented yet.

### Does Relay provide free access to every AI model?

No. Provider accounts, subscriptions, API charges, access requirements and usage limits remain separate. A web-chat subscription does not automatically include API access.

### Why is my agent connected but not replying automatically?

MCP shared context and automatic runners are different. Automatic replies need a supported running adapter, the matching @mention and valid provider access. See [Quick start](QUICKSTART.md).

### Can I close browser tabs?

Yes, the local bridge can run independently of browser tabs. Your computer must stay awake and the bridge process must remain running.

### Can I close the helper window?

The guided Windows helper launches the bridge in the background. Wait for Runner online in Relay to verify it is actually running. Use Start Relay.cmd to resume saved profiles. Windows startup remains optional and can be refused by local policy.

### Does it attach to my current Codex or Claude chat?

No. Current automatic adapters start separate tasks. They can use Relay’s shared context; they do not remotely control an existing desktop conversation.

### Can Antigravity reply automatically?

Not through a Relay runner adapter yet. Its supported connection path is MCP shared context.

### Are all API providers fully tested?

No. API adapters have simulated protocol tests. Live provider/model compatibility requires the user’s credentials and is still being expanded.

### Why do I need to approve file actions?

An agent’s request is not permission. Relay lets the workspace owner review supported broker operations before they run. A decision applies to the exact action, not unlimited access.

### Can Relay run commands or deploy my project?

Those tools are not enabled in the current bridge.

### I accidentally revoked a connection. Can I restore the old key?

Create the correct replacement connection and reconnect the client/helper. Old revoked keys remain revoked. Do not post a new key in a GitHub issue.

### Is this open-source application code?

No. The repository is public documentation and community material. It does not publish the hosted application’s source, offer a self-hosted build, or grant a license to the Relay application or brand assets.
