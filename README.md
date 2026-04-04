# shitadel-marketplace

Custom Claude Code plugin marketplace.

## Install

```
/plugin marketplace add CopyPasteFail/shitadel-marketplace
/plugin install postforge@shitadel-marketplace
```

## Plugins

| Name | Description |
|------|-------------|
| [postforge](https://github.com/CopyPasteFail/postforge) | LinkedIn post pipeline — discover topics, write posts, generate images, prepare drafts |

## After installing postforge

The plugin installs the skill and wires the MCP server config. You still need to:

1. Build the MCP backend (first time only):
   ```
   cd ~/.claude/plugins/postforge && npm install && npm run build
   ```
2. Run first-time auth:
   ```
   # In a postforge session, Claude will call linkedin-post-agent__ensure_auth
   ```

See [postforge INSTALL.md](https://github.com/CopyPasteFail/postforge/blob/main/.codex/INSTALL.md) for full setup details.

## Releasing a new version of postforge

When postforge ships a new commit that should be available to marketplace users:

1. Get the new SHA from the postforge repo:
   ```bash
   git -C /path/to/postforge rev-parse HEAD
   ```
2. Update the `sha` field in `.claude-plugin/marketplace.json`
3. Commit and push this repo:
   ```bash
   git add .claude-plugin/marketplace.json
   git commit -m "Bump postforge to <short-sha>"
   git push
   ```

Users who re-run `/plugin install postforge@shitadel-marketplace` will get the updated version.
