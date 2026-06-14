# Lumenwise

Lumenwise is an Obsidian plugin that turns RSS noise into filtered knowledge notes.

It fetches RSS or Atom feeds, asks an OpenAI-compatible LLM whether each item is
worth saving, and writes kept items into your Obsidian vault as structured
Markdown notes.

## What It Does

- Add RSS or Atom feeds in Obsidian settings.
- Enable or disable individual feeds.
- Fetch manually or on an interval.
- Deduplicate already processed items.
- Filter new items with an LLM.
- Save only high-value items as Markdown notes.
- Optional Chinese summary and bilingual key points.
- Supports OpenAI-compatible providers:
  - OpenAI
  - DeepSeek
  - Kimi
  - OpenRouter
  - Custom endpoint

## What It Is Not

Lumenwise is not a full RSS reader, crawler, graph system, canvas tool, or
embedding search engine. It is a semantic filter for getting useful feed items
into Obsidian with less noise.

## Installation

1. Download `lumenwise-v0.0.1.zip` from the latest GitHub Release.
2. Unzip it.
3. Copy the `lumenwise` folder into your Obsidian vault:

```text
<your-vault>/.obsidian/plugins/lumenwise/
```

4. Reload Obsidian.
5. Enable Lumenwise in Community Plugins.
6. Open Lumenwise settings and configure:
   - LLM provider
   - API key
   - feed URLs
   - optional Chinese translation

## Output Format

Lumenwise writes notes like this:

```md
# Article title

## Summary
English summary...

## 中文摘要
中文摘要...

## Key Points
- Point one
- Point two

## 中文要点
- 要点一
- 要点二

## Tags
#AI #research

## Source
https://example.com/article

## Metadata
- importance: 0.8
- created: 2026-06-15
- source: Lumenwise
- translated: true
```

## Source Code

This public repository is used for plugin distribution and release notes only.
The source code is not published here.

