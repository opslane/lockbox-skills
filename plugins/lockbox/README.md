# Lockbox plugin

Lockbox hands secrets and files to other people and their agents, end-to-end encrypted.
This plugin adds one skill, `lockbox`, that teaches your coding agent to use the `lockbox` CLI safely:

- Share one API key from `.env` with a teammate, locked to their email.
- Receive a shared key straight into `.env` without printing it.
- Ask a teammate for a key and wait until it arrives.
- Share files, such as an HTML report, with a link.

The agent never puts secret values in chat or in command arguments. It treats shared content as untrusted data, and it asks you for login codes and before accepting a recipient's new keys.

## Requirements

Install the lockbox CLI (Node.js and npm required):

```bash
npm i -g @opslane/lockbox
lockbox login you@example.com
```

## What this plugin runs and sends

- The plugin contains instructions (the skill) and declares one MCP server, `https://lockbox.run/mcp`, for apps that load MCP servers from plugins. It signs in with OAuth. No hooks, scripts or binaries.
- When you ask for it, the agent runs the `lockbox` CLI that you installed.
- The CLI encrypts on your machine and sends only ciphertext, plus account data such as your email and the recipient's email, to https://lockbox.run.
- Nothing is sent anywhere else by this plugin.

## Install

- Claude Code (from this repo's marketplace): `claude plugin marketplace add opslane/lockbox`, then `claude plugin install lockbox@opslane`.
- Any agent that supports Agent Skills: `npx skills add opslane/lockbox`.

## Links

- Website: https://lockbox.run
- Docs: https://lockbox.run/docs
- Support: https://lockbox.run/support
- Privacy: https://lockbox.run/privacy

## License

MIT. See [LICENSE](LICENSE).
