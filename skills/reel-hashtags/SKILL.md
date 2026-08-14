---
name: reel-hashtags
description: Researches real hashtag reach/competition for a topic or niche via live web search and returns a ranked, source-backed hashtag set (big/medium/niche mix) — instead of guessed tiers. Use when the user wants accurate or research-backed hashtags, asks "best hashtags for X", wants to double-check tag reach before posting, or when a reel-script caption's self-generated hashtags should be swapped for researched ones. Works for Instagram, TikTok, or YouTube Shorts.
---

# Reel Hashtag Researcher

`reel-script` writes a plausible hashtag mix by default — fine for most posts. This skill exists for when "plausible" isn't good enough: real reach/competition data instead of a guess.

## Step 1: Get the essentials

Ask only if missing: **niche/topic**, and **platform** (Instagram/TikTok/YouTube Shorts — default Instagram if unspecified, since tag culture differs slightly per platform).

## Step 2: Search live

Same rule as `reel-trends`: never answer from memory, hashtag "reach tiers" go stale.

If the web-search tool isn't loaded yet in this harness, load it first via `ToolSearch` with `select:WebSearch`. If no web-search tool is available after that, say so plainly: "I don't have live web search here, so I can't confirm real hashtag data — I can still give a generic mix if that's useful." Never invent volume numbers to fill the gap.

Once available, search with queries like:
- `"best hashtags for [niche] instagram 2026"`
- `"[niche] hashtag volume tiktok"`
- `"trending hashtags [niche] this week"`

## Step 3: Return the set

3–8 hashtags, mixed tiers:

| Hashtag | Tier | Why (reach/competition signal) | Source |
|---------|------|--------------------------------|--------|
| #… | Big (1M+) | … | [site](URL) |
| #… | Medium (100K–1M) | … | [site](URL) |
| #… | Niche | … | [site](URL) |

Rules:
- **Source column mandatory**, same as `reel-trends` — no traceable source, drop the row rather than list it.
- Don't state exact post-count numbers unless the source actually gives one — round/approximate language ("roughly 1M+ posts, per [source]") beats a fabricated precise figure.
- If search results are thin for a very narrow niche, say so and offer the closest broader niche's data instead of padding.

## Step 4: Hand off

If this was triggered mid-`reel-script` (a caption already exists with guessed hashtags), offer to swap the researched set into that caption in place of the guessed one. Otherwise end with: "Want these swapped into a reel-script caption? Give me the topic and I'll write one."
