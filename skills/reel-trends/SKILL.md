---
name: reel-trends
description: Finds current trending Reel/TikTok/Short topics, formats, audio for a niche via live web search — ranked, source-backed ideas. Trigger on "what's trending in X", viral idea requests, or finding a topic before scripting. Hands off to reel-script.
---

# Reel Trend Finder

Search-based, not written from memory — hand off to `reel-script` once a trend is picked.

## Step 1
Get niche + region/language if not given (default to user's language).

## Step 2: Search live
Never answer from memory — trends move in days. If WebSearch isn't loaded, call `ToolSearch` with `select:WebSearch` first; if still unavailable, say so and stop rather than guess. Run 2–3 queries: `"[niche] reel ideas trending 2026"`, `"[niche] tiktok trends this week"`, `"trending audio [niche] instagram reels"`. Prefer last 1–4 weeks; discard stale listicles.

## Step 3: Return ranked ideas
5–8 ideas:
| # | Idea | Why it's trending | Suggested angle | Source |
|---|------|-------------------|------------------|--------|
| 1 | … | … | … | [site](URL) |

Every row needs a real reason (spiking audio/format/news, not "could work") and a mandatory Source link — drop a row rather than list one without a source. Mix idea types if variety exists. Thin/generic results → say so, don't pad. Sources >4 weeks old → "recently trending," not "trending today."

## Step 4: Hand off
"Want the full script for any of these? Just say the number." Pass the pick's topic + angle into `reel-script` Step 1 (only ask for what's still missing).
