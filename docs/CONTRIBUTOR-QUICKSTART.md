# Your first Relay contribution

You do not need access to Relay's private application source to help.

## Choose a small, useful change

| You noticed… | A useful contribution |
| --- | --- |
| A setup step is confusing | Improve the wording in [Quick start](QUICKSTART.md). |
| A configuration example is incomplete | Suggest a tested, secret-free example in [Agent setup](AGENTS.md). |
| A connection is failing | Open a reproducible bug report with sanitized steps. |
| An agent is missing | Explain the client, protocol and authentication needs in an integration request. |
| A term is unclear | Improve the [FAQ](FAQ.md) with a focused explanation. |

Look for [good first issues](https://github.com/justokaywith/Relay/labels/good%20first%20issue) and [help wanted](https://github.com/justokaywith/Relay/labels/help%20wanted). Search before starting a duplicate.

## Edit in your browser

1. Open the documentation file on GitHub.
2. Select the pencil (**Edit this file**). GitHub may offer to fork the repository.
3. Make one focused improvement. Use **Preview** to check Markdown.
4. Propose the change with a short title and an explanation of what was unclear and how your change helps.
5. Submit a pull request against `main`.

No local installation or app build is needed for documentation edits.

## Or use Git

```sh
git clone https://github.com/YOUR-USERNAME/Relay.git
cd Relay
git switch -c docs/clearer-agent-setup
# Edit the relevant Markdown file.
git diff --check
git add docs/AGENTS.md
git commit -m "docs: clarify agent setup"
git push -u origin docs/clearer-agent-setup
```

Fork **justokaywith/Relay** first. Replace `YOUR-USERNAME` with your GitHub username. Then open a pull request to the upstream repository.

## Before submitting

- Follow [Contributing](../CONTRIBUTING.md) and the [Code of conduct](../CODE_OF_CONDUCT.md).
- Check links, Markdown preview and configuration syntax.
- Use placeholders instead of secrets. Remove account emails and private project names from screenshots.
- Say what you actually tested: client/version, operating system, connection type and result.
- Clearly separate proposed behaviour from a feature available today.
- Do not upload application source, installers or dependency changes.

Maintainers review accuracy, privacy and scope. A contribution or request does not guarantee a release date or reward.
