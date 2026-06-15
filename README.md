# Lumenwise

Lumenwise is an Obsidian plugin that turns RSS noise into filtered knowledge notes.

It fetches RSS or Atom feeds, asks an OpenAI-compatible LLM whether each item is
worth saving **for you**, and writes kept items into your vault as structured,
Dataview-ready Markdown notes.

## What It Does

- Add RSS or Atom feeds in Obsidian settings.
- **Describe your interests in plain language** — Lumenwise reads what you care
  about (and what you don't) and judges relevance accordingly. No rules,
  thresholds, or scores to configure.
- Filter new items with an LLM and save only what's worth keeping:
  - **Full notes** for high-value items (summary, key points, tags).
  - **Summary notes** for lighter, skim-only items.
  - Low-value items are filtered out silently, but logged (see below).
- **Dataview-ready frontmatter** on every note: `source`, `importance`, `tier`,
  `tags`, and dates — so you can query and group your knowledge base.
- A **source label** on each note so you can tell at a glance which feed it
  came from.
- An **inspectable filter log** at `<output>/_log/filtered-YYYY-MM.md` listing
  what was dropped and why — open it only if you suspect something was missed.
- A **sync button** in the left ribbon (spins while fetching), plus manual and
  interval-based auto-fetch.
- A **Reset seen items** command/button to re-evaluate everything (handy after
  changing your interests or deleting notes).
- Persistent deduplication using `title + link`.
- Optional Chinese (or other-language) summary and bilingual key points.
- A per-feed-per-run cap to bound LLM cost on busy feeds.
- OpenAI-compatible providers: OpenAI, DeepSeek, Kimi, OpenRouter, or a custom
  endpoint.

## What It Is Not

Lumenwise is not a full RSS reader, crawler, graph system, canvas tool, or
embedding search engine. It is a semantic filter for getting useful feed items
into Obsidian with less noise.

## Installation

Lumenwise is not yet in the Obsidian community plugin store.

### Via BRAT (recommended)

[BRAT](https://github.com/TfTHacker/obsidian42-brat) installs the plugin and
keeps it auto-updated from this repository.

1. Install **BRAT** from Community Plugins and enable it.
2. Run the command **BRAT: Add a beta plugin for testing**.
3. Paste this repository URL:

   ```text
   https://github.com/leoyang1984/lumenwise-public
   ```

4. BRAT downloads the latest release into your vault.
5. Enable **Lumenwise** in Community Plugins, then open its settings.

### Manual install

1. Download `main.js`, `manifest.json`, and `styles.css` from the
   [latest release](https://github.com/leoyang1984/lumenwise-public/releases/latest).
2. Put all three files in `<your-vault>/.obsidian/plugins/lumenwise/`.
3. Reload Obsidian and enable **Lumenwise** in Community Plugins.

## Setup

Open Lumenwise settings and configure:

- **Your interests** — one or two sentences describing what you want to read,
  and what you don't.
- **LLM provider** and **API key**.
- **Feed URLs**.
- Optional translation language.

Then click the ribbon sync button (or run **Fetch Now**).

## Output Format

Lumenwise writes notes with Dataview-ready frontmatter:

```md
---
source: "Simon Willison's Weblog"
link: "https://example.com/article"
importance: 0.8
tier: full
created: 2026-06-15
published: 2026-06-15
tags: [ai, llm]
generator: Lumenwise
---

# Article title

## Summary
English summary...

## 中文摘要
中文摘要...

## Key Points
- Point one
- Point two

## Source
[Simon Willison's Weblog](https://example.com/article)
```

Example Dataview query — group your knowledge base by source:

````md
```dataview
TABLE length(rows) AS notes
FROM "Lumenwise"
WHERE generator = "Lumenwise"
GROUP BY source
```
````

## Source Code

This public repository is used for plugin distribution and release notes only.
The compiled `main.js` is published here for installation; the TypeScript source
is not published.

## License

Lumenwise is available for non-commercial use only. See
[LICENSE.md](LICENSE.md).

Commercial use, resale, SaaS hosting, paid-client use, marketplace
redistribution, and commercial bundling require prior written permission.
