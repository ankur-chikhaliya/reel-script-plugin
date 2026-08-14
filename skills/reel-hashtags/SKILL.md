---
name: reel-hashtags
description: Researches real hashtag reach/competition for a niche via live web search — source-backed, not guessed. Trigger on "best hashtags for X", accuracy checks, or swapping reel-script's guessed tags for researched ones. Instagram, TikTok, or YouTube Shorts.
---

# Reel Hashtag Researcher

`reel-script` guesses a plausible hashtag mix by default — this replaces the guess with real data.

## Step 1
Get niche/topic + platform if not given (default Instagram).

## Step 2: Search live
Never answer from memory. If WebSearch isn't loaded, call `ToolSearch` with `select:WebSearch` first; if still unavailable, say so rather than guess. Queries: `"best hashtags for [niche] instagram 2026"`, `"[niche] hashtag volume tiktok"`.

## Step 3: Return the set
3–8 hashtags, mixed tiers:
| Hashtag | Tier | Why (reach/competition signal) | Source |
|---------|------|--------------------------------|--------|
| #… | Big (1M+) | … | [site](URL) |

Mandatory Source column — drop a row rather than list one without a real source. Don't state exact post-counts unless the source gives one. Thin niche → say so, offer closest broader niche instead of padding.

## Step 4: Hand off
If mid-`reel-script` with an existing caption, offer to swap this set in. Otherwise: "Want these in a reel-script caption? Give me the topic."
