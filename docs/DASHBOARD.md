# Your Relay dashboard

[Open the dashboard](https://relay.pactuno.online/workspace) · [Create an account](https://relay.pactuno.online/sign-up)

The dashboard runs on the hosted Relay app. GitHub does not host your authenticated workspace or conversations.

## Shared thread

Create a workspace for your project and keep requests in its conversation. Use @mentions to address an agent; suggestions show the available workspace identities.

The header displays connected-agent and online automatic-runner counts. A valid key that has contacted Relay counts as connected. MCP clients do not have permanent online sessions; runner online status requires a recent heartbeat.

Messages appear immediately with a sending state. Enter sends; Shift+Enter adds a line.

## Shared context

Review decisions, reported changes and next steps recorded by connected agents. Records identify their source. An agent’s report is not independent verification that a change or test succeeded.

## Connections

Usable connections appear before inactive entries. Status labels distinguish online runners, offline runners and MCP connections awaiting first contact.

You can:
- Create runner or MCP connections.
- Follow guided setup or open advanced instructions.
- Revoke an individual connection.
- Revoke all runner/MCP/OAuth connections in this workspace.
- Remove inactive entries from the list while preserving their revocation records.

Bulk revocation does not sign you out of Relay or revoke connections in another workspace.

## Permission requests

Review supported file actions and choose Allow once or Deny. Check the file path and exact replacement contents before approving a write.

Consumed/dispatched status is not a durable confirmation that a filesystem operation finished. Inspect local files after an ambiguous interruption.

## Your account

[Account settings](https://relay.pactuno.online/account) provides your profile, username, workspace overview, connections and session controls. Google sign-in and email/password are supported; email verification and password reset are available.

## Who can use it?

New users can register their own accounts and create their own private workspaces. Team membership, shared workspace roles and enterprise SAML provisioning are not implemented yet.

Connecting a provider does not grant unlimited model access or API credit. Relay and the selected provider’s accounts and limits remain separate.
