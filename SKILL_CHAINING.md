# Skill chaining convention

This plugin has more than one skill (`reel-script`, `reel-trends`) and may get more. There's no code execution layer connecting them — Claude Code skills are instruction files, not functions, so "auto-call" only ever happens because one skill's text tells the model to hand off to another. This file is the standing rule for how that must be written whenever a skill is added or edited.

## Rule

Every skill in this plugin must declare, in its own SKILL.md, both directions where they apply:

1. **Inbound gap → outbound offer.** If a skill is missing an input it needs and another skill in this plugin could supply it, the skill must offer that other skill by name in the same message it asks for the missing input — not a bare question. Example: `reel-script` missing a topic → offers `reel-trends` instead of just asking "what topic?".
2. **Completion → downstream offer.** If a skill's output is normally consumed by another skill in this plugin, it must end by offering that handoff explicitly, naming the next skill. Example: `reel-trends` finishes its list → offers to hand the pick into `reel-script`.
3. **Name the skill and the exact step it hands off to** ("pass into `reel-script` skill's Step 1"), so the model knows which file/behavior to switch into, not just "you could write a script."
4. **Never force the chain.** Always phrased as an offer the user can decline ("or just tell me X directly") — a skill must still work standalone with no chaining if the user provides everything itself.

## Current chain map

- `reel-trends` → completion → offers handoff to `reel-script` (Step 4)
- `reel-script` → missing topic → offers handoff to `reel-trends` (Step 1)

## When adding a new skill

Ask: does this skill produce something another skill in the plugin consumes, or need an input another skill produces? If yes, wire both directions per the rule above, update the chain map here, and bump plugin version (patch bump is enough — chaining text change, not new capability).
