# skills

Personal skills collection - forked from [mattpocock/skills](https://github.com/mattpocock/skills).

## Skills

| Skill | Bucket | Description |
|-------|--------|-------------|
| `obsidian-vault` | productivity | Search, create, and manage notes in Obsidian with wikilinks and index notes |

## Install

### skills.sh (any harness)
```bash
npx skills add elijah-musyoki/skills
```

### dotagents / opencode
```toml
# agents.toml
[[skills]]
name = "obsidian-vault"
source = "github:elijah-musyoki/skills"
path = "skills/productivity/obsidian-vault"
```

Or copy locally for dev:
```bash
cp -r skills/productivity/obsidian-vault ~/.config/opencode/skills/obsidian-vault
```

### Claude Code
```bash
/plugin add elijah-musyoki/skills
```

## Obsidian Vault Skill

Original was `personal/obsidian-vault` hardcoded to `/mnt/d/Obsidian Vault/AI Research/` - removed in [mattpocock/skills#c66bdee](https://github.com/mattpocock/skills/commit/c66bdee).

This fork makes the vault path configurable via `$OBSIDIAN_VAULT` env var instead.

```bash
export OBSIDIAN_VAULT="$HOME/Obsidian Vault"
```

## License

MIT - see [LICENSE](./LICENSE)
