---
name: reel-trends
description: Finds current trending Reel/TikTok/Short topics, formats, and audio for a given niche using live web search — returns a ranked list of trend-based content ideas, each with why it's trending and a suggested angle. Use whenever the user wants trending ideas, "what's trending in X", viral content ideas for their niche, or asks to find a topic before writing a script. Hands off to the reel-script skill to write the full script for any picked idea.
---

# Reel Trend Finder

Find what's actually trending right now for a niche, so the reel is riding a wave instead of guessing cold. This skill searches, it doesn't write scripts — hand off to `reel-script` once a trend is picked.

## Step 1: Get the niche

Ask only if not given: **niche/topic area** (e.g. "fitness", "my phone repair shop", "personal finance for students") and, if relevant, **region/language** (trends differ by country/language — default to what the user's been writing in).

## Step 2: Search live

Trends move in days, not months — never answer from memory. Use `WebSearch` (or the harness's web-search tool) with queries like:
- `"[niche] reel ideas trending 2026"`
- `"[niche] tiktok trends this week"`
- `"trending audio [niche] instagram reels"`
- `"[niche] viral video ideas [current month/year]"`

Run 2–3 varied queries. Prefer results from the last 1–4 weeks — check dates, discard stale listicles ("Top 50 Reel Ideas 2023" = not trending, ignore).

## Step 3: Return ranked ideas

Give 5–8 ideas, most relevant/fresh first:

### 📈 Trending ideas for [niche]

| # | Idea | Why it's trending | Suggested angle |
|---|------|-------------------|------------------|
| 1 | … | (format/audio/topic spiking + rough source) | (hook direction to take) |
| … | … | … | … |

Rules:
- Each idea must name *why* — a spiking audio, a format everyone's copying, a news/season hook, a challenge. Never "this could work" — trending means evidence found in Step 2, not a guess.
- Mix idea types: at least one trending-audio-led, one format/challenge-led, one topic/news-led, if search surfaces enough variety.
- If search results are thin or too generic for the niche, say so plainly — don't pad with invented "trends."
- No date-stamped urgency claims you can't back — if a source is >4 weeks old, label it "recently trending" not "trending today."

## Step 4: Hand off

End with: "Want me to write the full script for any of these? Just say the number." If the user picks one, pass that idea's topic + angle straight into the `reel-script` skill's Step 1 (topic + suggested angle already known — only ask for goal/language/length/link/response if still missing).
