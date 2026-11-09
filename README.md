<img src="https://since.dev/icon-512.png" alt="Since.dev" width="48" height="48">

# Since.dev for Cursor

The Since.dev plugin for Cursor: the MCP server, four skills and a rule, so the agent checks your packages, AI models and
runtimes against what changed before it touches them, and gets the fix.

## Install

[![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=since&config=eyJ1cmwiOiJodHRwczovL2FwaS5zaW5jZS5kZXYvbWNwIn0%3D)

**Add to Cursor** adds the server; sign in through your browser when Cursor asks. For the server, the skills and the rule
together, clone this repository into Cursor's local plugins folder and run **Developer: Reload Window**:

```sh
git clone https://github.com/since-dev/cursor ~/.cursor/plugins/local/since-dev
```

Without the plugin, copy [rules/since.mdc](rules/since.mdc) into `.cursor/rules/` and the [skills](skills) into
`.cursor/skills/` in your repository.

## What's inside

- **The server** at `https://api.since.dev/mcp`: 3 tools. `whats_changed` and `check_code` only read; `fix_code` opens fix pull requests, so Cursor asks before every call.
- **Skills:** [`since-before-upgrading`](skills/since-before-upgrading/SKILL.md), [`since-model-retirements`](skills/since-model-retirements/SKILL.md), [`since-what-changed`](skills/since-what-changed/SKILL.md), [`since-ci-and-runtimes`](skills/since-ci-and-runtimes/SKILL.md). They tell the agent when to check: before upgrades, when code names a model, before writing against something it learned in training, and when editing CI or runtimes.
- **A rule** ([rules/since.mdc](rules/since.mdc)) that attaches when a manifest, lockfile, Dockerfile, workflow or runtime version file is in context.

For Claude, Codex, Gemini and any other MCP client, see [Since-dev/mcp](https://github.com/since-dev/mcp). Documentation: https://since.dev/docs.

## License

MIT. See [LICENSE](LICENSE).
