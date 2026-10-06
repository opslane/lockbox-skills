# Lockbox skills and plugin

Send API keys and private files to someone else's agent, end-to-end encrypted.
[lockbox.run](https://lockbox.run)

This repo holds the agent-facing parts of Lockbox: the `lockbox` skill and a plugin bundle for
Claude Code, Codex and Cursor. The skill teaches your coding agent to use the `lockbox` CLI
(`npm i -g @opslane/lockbox`) so keys go from one `.env` to another without being printed or
pasted into chat.

## Install

**Any agent that reads skills (via [skills.sh](https://skills.sh)):**

```bash
npx skills add opslane/lockbox-skills
```

**Claude Code:**

```bash
claude plugin marketplace add opslane/lockbox-skills
claude plugin install lockbox@opslane
```

**Claude.ai and ChatGPT:** add `https://lockbox.run/mcp` as a connector. The Lockbox panel opens in
the chat.

Then install the CLI and sign in:

```bash
npm i -g @opslane/lockbox
lockbox login you@company.com
```

## What's here

| Path | What it is |
| --- | --- |
| `skills/lockbox/` | The skill (Agent Skills format) |
| `plugins/lockbox/` | The plugin bundle: the same skill, manifests for Claude Code, Codex and Cursor, and `mcp.json` |
| `.claude-plugin/marketplace.json` | A Claude Code marketplace with this one plugin |

The CLI and the Lockbox server are not in this repo. Docs: [lockbox.run/docs](https://lockbox.run/docs).
Security questions: [support@lockbox.run](mailto:support@lockbox.run).

## License

MIT, for the files in this repo. See [LICENSE](LICENSE).
