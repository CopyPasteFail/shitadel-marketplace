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
| [agents-md-builder](https://github.com/CopyPasteFail/agents-md-builder) | Generate and review repo-local AGENTS.md files for coding agents |

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
