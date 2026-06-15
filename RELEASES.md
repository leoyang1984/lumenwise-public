# Releases

## v0.1.0

Interest-driven filtering, note tiers, and a Dataview-ready note format.

### Added

- **Interest profile** — describe what you want to read in plain language; the
  LLM judges relevance to your interests instead of just general insight.
- **Note tiers** — high-value items become full structured notes, lighter items
  become summary (skim-only) notes.
- **Filter log** — discarded items are recorded with a reason in
  `<output>/_log/filtered-YYYY-MM.md`, so silent drops stay inspectable.
- **Dataview-ready YAML frontmatter** on every note (`source`, `link`,
  `importance`, `tier`, `tags`, `created`, `published`, `generator`).
- **Source label** on each note, taken from the feed title (or its domain).
- **Left-ribbon sync button** that spins while fetching.
- **Reset seen items** command and settings button to re-evaluate everything.
- **Per-feed-per-run cap** to bound LLM cost on busy feeds.

### Changed

- Notes now lead with frontmatter; the old `## Metadata` / `## Tags` blocks are
  replaced by frontmatter fields.

### Install

This release supports [BRAT](https://github.com/TfTHacker/obsidian42-brat). Add
`https://github.com/leoyang1984/lumenwise-public` as a beta plugin, or download
`main.js`, `manifest.json`, and `styles.css` from the release and place them in
`<your-vault>/.obsidian/plugins/lumenwise/`.

### Known Notes

- Notes written before v0.1.0 are not retroactively updated to the new format.
- The plugin requires an API key for the configured LLM provider.
- This repository does not publish source code.

## v0.0.1

Initial public plugin release.

### Added

- RSS and Atom feed management in Obsidian settings.
- Manual fetch and interval-based auto-fetch.
- Persistent deduplication using `title + link`.
- LLM keep/skip filtering through OpenAI-compatible chat completions APIs.
- Provider presets for OpenAI, DeepSeek, Kimi, OpenRouter, and Custom.
- Markdown note writer for kept items.
- Optional Chinese summary and bilingual key points.
- Lightweight UI localization following Obsidian language.
- More conservative importance scoring guidance.

### Install

Download `lumenwise-v0.0.1.zip` from the GitHub Release and copy the extracted
`lumenwise` folder into:

```text
<your-vault>/.obsidian/plugins/lumenwise/
```

Then reload Obsidian and enable the plugin.

### Known Notes

- Existing notes are not retroactively translated.
- The plugin requires an API key for the configured LLM provider.
- This repository does not publish source code.
