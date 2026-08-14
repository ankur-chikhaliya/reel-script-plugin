# Reel Script Writer

Claude Code plugin that writes complete short-form video scripts — Instagram Reels, TikToks, YouTube Shorts — built for retention, not just words on a page.

## What you get, every time

- 🎬 3 hook options, each a different psychological angle
- Second-by-second beats table (voiceover + on-screen shot list)
- One clear CTA (never stacked)
- Ready-to-post caption with hashtags
- Plain voiceover-only block for TTS / recording
- Works in any language — including natural Hinglish and other code-switched styles

## Installation

```bash
/plugin marketplace add ankur-chikhaliya/reel-script-plugin
/plugin install reel-script@reel-script-plugin
```

## Usage

### Write a script

**Auto-trigger** — just ask naturally:
```
make me a reel about my phone store's diwali offer
```

**Explicit command:**
```
/reel-script diwali offer at my phone store
```

### Find trending ideas first

**Auto-trigger:**
```
what's trending in fitness reels right now
```

**Explicit command:**
```
/reel-trends fitness
```

Returns a ranked list of current trend-based ideas (live web search, not guesses) — pick one and it hands off straight into `reel-script` for the full write-up.

### Research real hashtags instead of guessed ones

**Auto-trigger:**
```
best hashtags for home fitness on instagram
```

**Explicit command:**
```
/reel-hashtags home fitness
```

`reel-script`'s caption hashtags are a best-guess mix by default. This researches real reach/competition data (source-backed, live search) and can swap the result into an existing caption.

## Example

**Input:** "reel for my phone store, diwali offer"

**Output:**
- 3 hooks (curiosity gap, direct callout, result-first)
- Beats table with timestamps 0–20s
- CTA: "Store ka naam DM karo — offer price bhej dunga"
- Caption + hashtags
- Clean voiceover block

## License

MIT
