# obsidian-markdown

> 🇰🇷 [한국어 README](./README.ko.md)

**Obsidian Flavored Markdown reference and creation tool: wikilinks, embeds, callouts, properties, and advanced syntax.**

## Prerequisites

- **Obsidian Vault** — an active Obsidian vault (local or cloud-synced)
- **Obsidian MCP Server** — read-only access for `search_notes`, `read_note`, `get_frontmatter`
- **Claude Cowork or Claude Code** environment

## Goal

obsidian-markdown provides both a reference and execution engine for Obsidian-specific syntax — wikilinks, embeds, callouts, frontmatter properties, block references, comments, and tags — ensuring correct formatting across your vault.

## When & How to Use

Deploy whenever creating, editing, or refactoring notes within an Obsidian vault. Use as reference for syntax recall or as execution tool for systematically adding Obsidian features to existing markdown.

## Use Cases

| Scenario | Prompt | What Happens |
|---|---|---|
| New note with full features | `"Create note on Strategic Planning with wikilinks, properties, callouts"` | Frontmatter→wikilinks→callouts→block references→validated syntax |
| Convert external links | `"Refactor: convert links to wikilinks, add properties, create callout summaries"` | Link targets→wikilinks→frontmatter properties→callout wrapping |
| Connected knowledge base | `"Add embeds and bidirectional links throughout project folder"` | Hierarchical structure→wikilinks→embeds→properties→block references |

## Key Features

- Wikilinks: `[[Note Name]]` with optional alias; auto-generates backlinks
- Embeds: `![[Note Name]]` or `![[Note Name#^block-id]]`; live updates
- Callouts: 12 types (note, tip, important, warning, etc.)
- Frontmatter properties: YAML metadata for sorting, filtering, automation
- Block references: `^block-id` for precise internal citations
- Comments: `%% comment %%` invisible in preview
- Syntax validation for correct formatting

## Works With

- **[html-div-style](https://github.com/jasonnamii/html-div-style)** — visual styling maintaining Obsidian compatibility
- **[deliverable-engine](https://github.com/jasonnamii/deliverable-engine)** — structures complex notes with Obsidian syntax

## Installation

```bash
git clone https://github.com/jasonnamii/obsidian-markdown.git ~/.claude/skills/obsidian-markdown
```

## Update

```bash
cd ~/.claude/skills/obsidian-markdown && git pull
```

Skills placed in `~/.claude/skills/` are automatically available in Claude Code and Cowork sessions.

## Part of Cowork Skills

This is one of 25+ custom skills. See the full catalog: [github.com/jasonnamii/cowork-skills](https://github.com/jasonnamii/cowork-skills)

## License

MIT License — feel free to use, modify, and share.
