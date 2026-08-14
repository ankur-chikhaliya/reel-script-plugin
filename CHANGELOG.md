# Changelog

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
