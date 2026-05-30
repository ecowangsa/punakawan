# Changelog

Notable changes to Punakawan. The version users install is the `version` field in
[`.claude-plugin/plugin.json`](.claude-plugin/plugin.json); this project follows
[semantic versioning](https://semver.org). To see your installed version and pick
up updates, run `/plugin` in Claude Code.

## 0.1.0 - 2026-05-30

First release packaged as a Claude Code **plugin**, distributed from its own
marketplace (this repo) so the installed version is tracked and updates are
visible through `/plugin`.

- Added `.claude-plugin/plugin.json` and `.claude-plugin/marketplace.json`; the
  skill loads from the repo root (`"skills": ["./"]`), so no files moved.
- The typed command is now namespaced `/punakawan:panel` (plugin skills are always
  `plugin:skill`). The plain-language trigger ("convene the punakawan", "second
  opinion", ...) is unchanged - it keys off the skill description, not the command.
- Panel behavior is unchanged from the prior standalone skill: nine wayang lenses
  seated by question, the zero-cost divergence gate, the uniform `--effort` dial,
  and Semar's verdict-first synthesis.

### Upgrading from the standalone skill

Earlier the skill was installed by `git clone`-ing into `~/.claude/skills/punakawan`.
Remove that copy so it does not shadow the plugin, then install from the marketplace:

```sh
rm -rf ~/.claude/skills/punakawan
```

```
/plugin marketplace add ecowangsa/punakawan
/plugin install punakawan@punakawan
```
