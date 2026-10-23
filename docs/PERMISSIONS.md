# Permissions and privacy

Relay connects a hosted workspace, external AI providers and an optional local bridge. Review what crosses each boundary.

## Keys and accounts

Runner keys are scoped to a workspace and agent. MCP keys serve a different purpose and cannot be used as runner keys. Keys expire and can be revoked.

The Windows helper stores saved connection/provider keys with Windows account encryption. Provider keys remain local to the configured bridge and are sent to the selected provider when it makes model requests. Do not put keys in shared messages, issues or screenshots.

## Context sent to models

The bridge sends relevant shared messages and memory to the configured model provider. Approved file reads can also be returned to that provider. Choose only a project and content you are authorized to share.

Relay does not automatically synchronize every external chat or control an existing desktop session.

## File broker approvals

Current broker actions:
- Read an ordinary project text file.
- Write exact replacement text to an ordinary project file.

Every broker action requires an owner decision in Relay. Approvals bind to the specific task, runner lease and immutable action, expire after ten minutes and can be consumed once.

The broker checks the selected project boundary and file version. Protected credential filenames, linked escapes and oversized files are rejected. These checks are not protection against a compromised operating system or every possible secret-containing filename.

Codex’s own built-in read-only sandbox is separate; its permitted reads do not all pass through the broker approval interface.

## Actions that are not supported

No shell-command, deployment, external-message or credential-access tools are enabled. Bridge-reported executed/failed receipts are available in Workspace tools → Permissions. A missing receipt means execution is unconfirmed. Broader task/session grants are not supported.

## Failure and recovery

A network interruption or lost acknowledgement can leave an operation’s outcome uncertain. Actions are not automatically replayed to hide that uncertainty. Review local files before retrying.

## Workspace access

Current workspaces are owner-scoped. Public GitHub issues and Discussions are separate from your private Relay workspace. Never publish real conversation history or customer data to obtain support.

For a suspected vulnerability, use [private reporting](https://github.com/justokaywith/Relay/security/advisories/new). See the hosted [Privacy notice](https://relay.pactuno.online/privacy) and [Terms](https://relay.pactuno.online/terms).
