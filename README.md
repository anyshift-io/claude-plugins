# anyshift / claude-plugins

[![License](https://img.shields.io/badge/license-Apache_2.0-blue.svg)](./LICENSE)

Public [Claude Code](https://claude.com/claude-code) plugin marketplace maintained by [Anyshift](https://www.anyshift.io).

One marketplace, one install command, every Anyshift skill.

## Install

In a Claude Code session:

```
/plugin marketplace add anyshift-io/claude-plugins
/plugin install annie-skills@anyshift
```

That's it. The skill is now loaded and the agent will reach for it whenever the user asks something that maps to Annie or the Anyshift MCP surface.

To see what else is in the marketplace:

```
/plugin marketplace browse anyshift
```

To update later (after we ship a new plugin or a new version of an existing one):

```
/plugin marketplace update anyshift
```

## What's in here

| Plugin | What it does | Source |
|---|---|---|
| `annie-skills` | Teaches the agent how to drive the Annie CLI and the Anyshift MCP server: install + auth, the 5 read-only tools (`get_resource_graph`, `get_recent_changes`, `get_dependents`, `get_blast_radius`, `get_temporal_diff`), worked examples, failure modes. | [`anyshift-io/annie-skills`](https://github.com/anyshift-io/annie-skills) |
| `sre-skills` | Vendor-neutral SRE methodology skills: investigate a live incident, analyze change impact, hand over oncall, author a postmortem, audit reliability. Runs offline against fixtures, no credentials required. | [`anyshift-io/sre-skills`](https://github.com/anyshift-io/sre-skills) |

More plugins ship here as they land. See the [`plugins` array in `.claude-plugin/marketplace.json`](./.claude-plugin/marketplace.json) for the canonical list.

## Related repositories

- [`anyshift-io/annie-skills`](https://github.com/anyshift-io/annie-skills), Anyshift-specific skills (vendor-bound: needs Annie).
- [`anyshift-io/sre-skills`](https://github.com/anyshift-io/sre-skills), vendor-neutral SRE methodology skills.
- [`anyshift-io/awesome-sre-skills`](https://github.com/anyshift-io/awesome-sre-skills), curated index of SRE skills, MCP servers, and reading.

## Contributing

Plugin contributions live in their source repos, not here. Send patches there. This repo holds only the marketplace catalog (`.claude-plugin/marketplace.json`).

If you want to propose a new plugin for the catalog, open an issue with a link to the plugin repo and a short pitch on what it does. Reviewers check: the plugin has a valid `.claude-plugin/plugin.json`, the skill / command / agent passes `claude plugin validate`, and the scope fits Anyshift's positioning (SRE, infrastructure-aware agents).

## License

[Apache 2.0](./LICENSE). The catalog itself is licensed Apache 2.0; each listed plugin carries its own license, see the plugin's repo.
