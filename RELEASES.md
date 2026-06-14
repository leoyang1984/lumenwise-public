# Releases

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
