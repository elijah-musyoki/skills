---
name: obsidian-vault
description: Search, create, and manage notes in the Obsidian vault with wikilinks and index notes. Use when user wants to find, create, or organize notes in Obsidian.
---

# Obsidian Vault

## Vault location

> **Configurable** - set via `OBSIDIAN_VAULT` env var or ask the user on first use. Do NOT hardcode.
>
> Default suggestion: `~/Obsidian Vault` or `~/Documents/Obsidian Vault`
>
> On first run, if `OBSIDIAN_VAULT` is not set, ask: "Where is your Obsidian vault?"

Mostly flat at root level - adapt to user's actual structure.

## Naming conventions

- **Index notes**: aggregate related topics (e.g., `Skills Index.md`, `RAG Index.md`, `Projects Index.md`)
- **Title case** for all note names
- No folders for organization by default - use links and index notes instead (respect user's existing folder structure if they have one)

## Linking

- Use Obsidian `[[wikilinks]]` syntax: `[[Note Title]]`
- Notes link to dependencies/related notes at the bottom
- Index notes are just lists of `[[wikilinks]]`

## Workflows

### Search for notes

```bash
# Search by filename
find "$OBSIDIAN_VAULT" -name "*.md" | grep -i "keyword"

# Search by content
grep -rl "keyword" "$OBSIDIAN_VAULT" --include="*.md"
```

Or use Grep/Glob tools directly on the vault path.

### Create a new note

1. Use **Title Case** for filename
2. Write content as a unit of learning
3. Add `[[wikilinks]]` to related notes at the bottom
4. If part of a numbered sequence, use the hierarchical numbering scheme
5. Write to `$OBSIDIAN_VAULT/<Title>.md`

### Find related notes

Search for `[[Note Title]]` across the vault to find backlinks:

```bash
grep -rl "\[\[Note Title\]\]" "$OBSIDIAN_VAULT"
```

### Find index notes

```bash
find "$OBSIDIAN_VAULT" -name "*Index*"
```

## Setup

1. Set env var: `export OBSIDIAN_VAULT="$HOME/Obsidian Vault"`
2. Or create `~/.config/obsidian-vault/path` with the vault path
3. Skill will prompt if not found
