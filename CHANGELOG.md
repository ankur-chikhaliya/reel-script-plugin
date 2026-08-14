# Changelog

## [1.4.2] - 2026-08-14

### Fixed
- `reel-script`'s caption→`reel-hashtags` offer now names the exact step ("`reel-hashtags` Step 1"), matching `SKILL_CHAINING.md` rule 3 which the other two handoffs already followed

## [1.4.1] - 2026-08-14

### Changed (token reduction)
- All 3 skill descriptions shortened (~50% shorter frontmatter) — these load into context every turn regardless of use, so this is the real recurring saving
- All 3 SKILL.md bodies trimmed — condensed lists/tables, removed redundant phrasing, shorter worked example. One-time cost when a skill actually triggers, smaller impact than the description cut but still real
- plugin.json top-level description shortened to match

### Tried and reverted
- Attempted converting `reel-trends`/`reel-hashtags` to command-only (no skill auto-trigger) to drop their standing listing cost to zero. Tested live: personal `~/.claude/commands/` files get surfaced in the skill listing the same way skills do, so this saved nothing and only cost the natural-language auto-trigger. Reverted — all 3 remain skills.

## [1.4.0] - 2026-08-14

### Added
- New `reel-hashtags` skill + `/reel-hashtags` command: researches real hashtag reach/competition via live web search, source-backed (same mandatory-Source pattern as `reel-trends`), can swap results into an existing `reel-script` caption
- `reel-script` hook angles expanded: pattern interrupt, loss aversion, social proof cold open + a cross-hook specificity rule (concrete numbers/timeframes beat vague phrasing)
- `reel-script` CTA rule: same specificity principle applied to CTA wording
- `reel-script` caption step now mentions `reel-hashtags` as an optional upgrade over its own guessed tags (not run automatically)
- `SKILL_CHAINING.md` chain map updated for the 3-skill plugin

## [1.3.4] - 2026-08-14

### Fixed
- `commands/reel-script.md`: no-args fallback no longer says "ask the user for the topic first" (contradicted the skill's no-topic chaining offer) — now points at Step 1's actual no-topic behavior (offer `reel-trends`)
- `reel-script` evals: added 4 cases that were previously untested — link/response fields used correctly in CTA/caption, beats-sum-to-declared-Length, claims guardrail on unbacked health/finance topics, and the no-topic → offer-reel-trends chaining

## [1.3.3] - 2026-08-14

### Changed
- GitHub account renamed `ankur1423` -> `ankur-chikhaliya`. Updated repo path everywhere: plugin.json (author.url, homepage, repository), README install command, git remote origin. GitHub auto-forwards the old URL for a while, but all references now point directly to the new path.

## [1.3.2] - 2026-08-14

### Changed
- Contact email in plugin.json author field -> hello@ankurchikhaliya.com (metadata only; git commit email unchanged since it must stay the GitHub-verified address to keep commits linked to the account)

## [1.3.1] - 2026-08-14

### Changed
- Author display name updated to "ankur-chikhaliya" (plugin.json, LICENSE). GitHub repo path stays `ankur1423` — that's the real account username, unaffected by this cosmetic change.

## [1.3.0] - 2026-08-14

### Added
- `reel-script` now offers `reel-trends` when called with no topic at all, instead of a bare "what's it about?" — two-way chain now (`reel-trends`→`reel-script` already existed, added `reel-script`→`reel-trends`)
- `SKILL_CHAINING.md`: standing convention doc — any future skill added to this plugin must declare its inbound-gap and completion handoffs to other skills in the plugin, so chaining stays automatic instead of siloed

## [1.2.2] - 2026-08-14

### Fixed
- `reel-trends`: added mandatory Source column (site name + link) to the trending-ideas table — every row must trace back to an actual search result, no more "rough source" vagueness

## [1.2.1] - 2026-08-14

### Fixed
- `reel-trends`: load WebSearch via ToolSearch if deferred, and explicitly refuse to guess trends from memory when no search tool is available
- `reel-script`: beats must sum to the declared Length exactly (no more drift between header and actual runtime)
- `reel-script`: added a claims guardrail — no stated-as-fact numbers/guarantees/medical-financial-legal claims unless user supplied them; disclaimer line added for those topics when unbacked
- Added `reel-trends` evals (clear-trend niche + thin-data niche) — was previously untested
- `plugin.json` keywords now include trend/trending/viral

## [1.2.0] - 2026-08-14

### Added
- New `reel-trends` skill + `/reel-trends` command: finds current trending topics/formats/audio for a niche via live web search, returns ranked ideas with why-it's-trending evidence
- Hands off picked trend idea straight into `reel-script` for full script write

## [1.1.0] - 2026-08-14

### Added
- Two new optional intake fields, generic for any content type (not business-only): link/handle to point viewers to, and response method (DM keyword, comment word, email, phone, link in bio, or none)
- Fields only asked when the goal actually needs them — skipped for pure entertainment/education reels
- CTA and caption now use the given link/response method when present

## [1.0.0] - 2026-08-14

### Added
- Initial release: `reel-script` skill (auto-trigger) + `/reel-script` slash command
- Hook generation (3 angles), beats table, single CTA, caption + hashtags, voiceover-only block
- Multi-language support including Hinglish-style code-switching
