---
name: obsidian-vault
description: Search, create, and manage notes in the Obsidian vault with wikilinks and index notes. Use when user wants to find, create, or organize notes in Obsidian.
---

# Obsidian Vault

## Vault location

`/home/elijah/Documents/obsidian-vault/vault`

> Configurable via `OBSIDIAN_VAULT` env var. Defaults to your vault above. If moved, update the env var or this file.

Mostly flat at root level - adapt to your actual structure. Current vault has `.obsidian/` config + `Welcome.md`.

## Naming conventions

- **Index notes**: aggregate related topics (e.g., `Skills Index.md`, `RAG Index.md`, `Projects Index.md`)
- **Title case** for all note names
- No folders for organization by default - use links and index notes instead (respect existing folder structure if you have one)

## Linking

- Use Obsidian `[[wikilinks]]` syntax: `[[Note Title]]`
- Notes link to dependencies/related notes at the bottom
- Index notes are just lists of `[[wikilinks]]`

## Workflows

### Search for notes

```bash
# Search by filename
find "/home/elijah/Documents/obsidian-vault/vault" -name "*.md" | grep -i "keyword"

# Search by content
grep -rl "keyword" "/home/elijah/Documents/obsidian-vault/vault" --include="*.md"
```

Or use Grep/Glob tools directly on the vault path.

### Create a new note

1. Use **Title Case** for filename
2. Write content as a unit of learning
3. Add `[[wikilinks]]` to related notes at the bottom
4. If part of a numbered sequence, use the hierarchical numbering scheme
5. Write to `/home/elijah/Documents/obsidian-vault/vault/<Title>.md`

### Find related notes

Search for `[[Note Title]]` across the vault to find backlinks:

```bash
grep -rl "\[\[Note Title\]\]" "/home/elijah/Documents/obsidian-vault/vault"
```

### Find index notes

```bash
find "/home/elijah/Documents/obsidian-vault/vault" -name "*Index*"
```

## Setup

- Vault lives at `/home/elijah/Documents/obsidian-vault/vault`
- Override with: `export OBSIDIAN_VAULT="/home/elijah/Documents/obsidian-vault/vault"`
